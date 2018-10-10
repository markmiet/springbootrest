pipeline {
  agent {
    docker {
      image 'maven:3.5.4-jdk-8-alpine'
      args '-v /root/.m2:/root/.m2'
    }

    triggers {
        pollSCM 'H/1 * * * *'
    }
  }

  stages {
    stage('dev') {
      steps {
        echo 'testi jhjh'
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

}
