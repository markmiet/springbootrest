pipeline {
  agent {
    docker {
      image 'maven:3.5.4-jdk-8-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('dev') {
      steps {
        echo 'testi jhjh marko'
      }
    }
    stage('build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('archive the artifacts') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }
  }
  triggers {
    pollSCM('H/1 * * * *')
  }
}