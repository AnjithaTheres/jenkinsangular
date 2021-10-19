pipeline {
  tools {
    nodejs 'Node16'
  }
    agent any
    stages {
        stage('Check version') {
            steps {
                echo 'Cleaning..'
                bat 'npm --version'
            }
          post{ 
          success{
             slackSend message : 'Successfully cleaned'
       
            }
          failure {
           slackSend message : 'Cleaning failed'
        }
        }
        }
        stage('Install dependencies') {
            steps {
                echo 'Install deps..'
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'npm test'
            }
        }
        stage('Package') {
            steps {
                echo 'npm build'
            }
        }
    }
}
