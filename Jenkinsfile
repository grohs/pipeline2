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
    stage('') {
      steps {
        sh '''git checkout master
git pull
git merge staging
git checkout master
git push'''
      }
    }
  }
}