pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building nodejs app'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the app'
            echo 'chrome driver path is ${chromeDriverPath}'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy the app in Aws'
        input(message: 'Do you want to deploy?', id: 'OK')
      }
    }

  }
  environment {
    chromeDriverPath = 'C:\\drivers'
  }
}