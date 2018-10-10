pipeline {
  agent any
  stages {
    stage('dev') {
      steps {
        git(url: 'https://github.com/markmiet/springbootrest', branch: 'origin', credentialsId: 'markmiet:Koirayes777!', poll: true)
      }
    }
  }
}