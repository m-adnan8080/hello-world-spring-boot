pipeline {
  agent any
    tools{
      maven '3.6.3'
    }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -version'
        sh 'mvn clean package'
      }
    }
  }

  post {
    always {
      cleanWs()
    }
  }
}
