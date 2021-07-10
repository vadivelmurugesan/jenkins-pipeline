pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        sh '''sh "chmod +x -R ${env.WORKSPACE}"
jenkins/build.sh'''
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
        sh '''sh "chmod +x -R ${env.WORKSPACE}"
jenkins/test-all.sh'''
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying'
        sh '''sh "chmod +x -R ${env.WORKSPACE}"
jenkins/deploy.sh'''
      }
    }

  }
}