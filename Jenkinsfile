pipeline {
  agent any
  stages {
    stage('git staging') {
      steps {
        git(url: 'https://github.com/grohs/pipeline2.git', branch: 'staging')
      }
    }
    stage('deploy') {
      steps {
        sh '''/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQube/bin/sonar-scanner -Dsonar.host.url=http://192.168.0.14:9000 -Dsonar.projectName=pipeline2_staging -Dsonar.projectVersion=1.0 -Dsonar.projectKey=pipeline2.com.br -Dsonar.sources=. -Dsonar.projectBaseDir=/var/lib/jenkins/workspace/pipeline2_staging
'''
      }
    }
    stage('merge') {
      steps {
        sh '''git checkout staging
git pull https://github.com/grohs/pipeline2.git staging
git merge master
git checkout master
git add -all
git commit -m "Merged branch staging into master"
git push https://github.com/grohs/pipeline2.git master'''
      }
    }
  }
}