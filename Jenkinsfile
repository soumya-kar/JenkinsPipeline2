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

        stage('TestLog') {
          environment {
            localVar = 'Test variable'
          }
          steps {
            writeFile(file: 'TestLog.txt', text: "This is automated log from Blue Ocean pipeline driver and local variable ${localVar} ")
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

    stage('Archive File') {
      steps {
        archiveArtifacts 'TestLog.txt'
      }
    }

  }
  environment {
    chromeDriverPath = 'C:\\drivers'
  }
}