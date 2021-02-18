pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '/opt/apache-maven-3.6.3/bin/mvn -version'
        sh '/opt/apache-maven-3.6.3/bin/mvn clean package'
      }
    }
  }

  post {
    always {
      cleanWs()
    }
  }
}
