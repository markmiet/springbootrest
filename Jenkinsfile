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
    stage('Varmistuskysymys') {
      steps {
        input(message: 'Haluatko varmasti kaynnistaa', id: '1', ok: 'mennaan')
      }
    }
    stage('ajo') {
      steps {
        sh '''echo alku
cd ./target
java -jar demo-18.0.2.jar
echo testi
'''
      }
    }
  }
}