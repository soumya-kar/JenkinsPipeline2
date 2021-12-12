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
        input(message: 'Do you want to deploy?', id: 'OK')
        echo 'Deploy the app in Aws'
      }
    }

  }
  environment {
    chromeDriverPath = 'C:\\drivers'
  }
}