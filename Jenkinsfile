pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        sh './mvnw clean install'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
        sh './mvnw verify'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }

  }
}