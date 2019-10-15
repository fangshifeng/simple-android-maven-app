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
	echo 'Hello,Maven'
        sh 'mvn --version'
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
