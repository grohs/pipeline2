pipeline {
  agent any
  stages {
    stage('git master') {
      steps {
        git(url: 'https://github.com/grohs/pipeline2.git', branch: 'staging')
      }
    }
  }
}