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
    stage('error') {
      steps {
        sh '''git config --global push.default matching
git checkout master
git pull
git merge staging
git checkout master
git push'''
      }
    }
  }
}