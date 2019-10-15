pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Build Develop APK') {
      when {
        branch 'master'
      }     
      steps {
        sh './gradlew clean assembleDebug'
      }
      post {
        failure {
          echo "Build Develop APK Failure!"
        }
        success {
          echo "Build Develop APK Success!"
        }
      }
    }
    stage('Deliver') { 
      steps {
          sh './jenkins/scripts/deliver.sh' 
      }
    }
  }
}
