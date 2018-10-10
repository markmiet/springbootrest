pipeline {
  agent {
    docker {
      args 'v /root/.m2:/root/.m2'
      image 'maven:3.5.4-jdk-8-alpine'
    }

  }
  stages {
    stage('dev') {
      steps {
        echo 'testi'
      }
    }
    stage('build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
  }
}