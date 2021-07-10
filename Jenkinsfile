pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        sh "chmod +x -R '${env.WORKSPACE}'"
        sh 'jenkins/build.sh'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
        sh "chmod +x -R '${env.WORKSPACE}'"
        sh 'jenkins/test-all.sh'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying'
        sh "chmod +x -R '${env.WORKSPACE}'"
        sh 'jenkins/deploy.sh'
      }
    }

  }
}