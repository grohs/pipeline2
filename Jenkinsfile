pipeline {
  agent any
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/grohs/pipeline2.git', branch: 'staging')
      }
    }
    stage('Bora?') {
      steps {
        input(message: 'Bora GO?', ok: 'Proceder')
      }
    }
    stage('Merge') {
      steps {
        sh '''git config --global push.default matching
git checkout master
git pull
git merge staging
git checkout master	
git remote set-url origin git@github.com:grohs/pipeline2.git
git push https://github.com/grohs/pipeline2.git master'''
      }
    }
  }
}