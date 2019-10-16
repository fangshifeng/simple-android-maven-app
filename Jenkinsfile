pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
  }

  stages {
    stage('Build Develop APK') {     
      steps {
        sh './gradlew clean assembleDebug'
      }
      post {
        failure {
          echo "Duild Develop APK Failure!"
        }
        success {
          echo "Build Develop APK Success"
        }
      }
    }

    stage('Example Test') { 
      steps {
        echo 'Hello JDK'
        sh 'java -version' 
      }
    }


  }
}
