pipeline {
  agent any
  tools{
    Maven 'apache-maven-3.6.0'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn-version'
        sh 'mnv clean package'
      }
    }
  }

  post {
    always {
      cleanWs()
    }
  }
}
