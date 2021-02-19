pipeline {
  agent any
  tools {
    maven '3.6.3'
  }
    // docker {
    //   image 'maven'
    //   args '-v $HOME/.m2:/root/.m2'
    // }
  stages {
    stage('Quality Gate Status Check'){
      steps{
        script{
          withSonarQubeEnv('sonarserver'){
            sh "mvn sonar:sonar"
          }
          timeout(time: 5, unit: 'MINUTES'){
            def qg = waitForQualityGate()
            if (qg.Status != 'OK'){
              error "Pipeline aborted due to quality gate failure : ${qg.Status}"
            }
          }
          sh 'mvn clean package'
          sh 'cp target/myproject-0.0.1-SNAPSHOT.jar $HOME/data/'
        }
      }
    }
    // stage('Build') {
    //   steps {
    //     sh 'mvn -version'
    //     sh 'mvn clean package'
    //     sh 'cp target/myproject-0.0.1-SNAPSHOT.jar $HOME/data/'
    //   }
    // }
  }

  post {
    always {
      cleanWs()
    }
  }
}
