pipeline {
  agent any
  tools {
    maven '3.6.3'
  }
  /*{
    docker {
      image 'maven'
      args '-v $HOME/.m2:/root/.m2'
    }*/
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
