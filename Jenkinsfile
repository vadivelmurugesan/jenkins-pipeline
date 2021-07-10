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
      parallel {
        stage('Test') {
          steps {
            echo 'Testing'
            sh './mvnw verify'
            junit 'target/**/*.xml'
          }
        }

        stage('Integration Testing') {
          steps {
            echo 'Running Integration Tests'
          }
        }

        stage('Performance Testing') {
          steps {
            timeout(time: 10) {
              echo 'Performance Testing'
            }

          }
        }

      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      steps {
        input(message: 'Shall we deploy?', ok: 'Yes')
        echo 'Deployed'
      }
    }

  }
}