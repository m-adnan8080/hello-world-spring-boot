pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''sh "mvn -version"
sh "mnv clean package"'''
      }
    }

  }
}