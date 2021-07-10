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
        junit 'target/**/*.xml'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }

  }
}