pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh "mvn -version"
        sh "mnv clean package"
      }
    }

  }
}
