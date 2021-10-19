pipeline {
  tools {
    nodejs 'Node16'
  }
    agent any
    stages {
        stage('Check version') {
            steps {
                echo 'Checking..'
                bat 'npm --version'
            }
          post{ 
          success{
             slackSend message : 'Successfully checked'
       
            }
          failure {
           slackSend message : 'Checking failed'
        }
        }
        }
        stage('Install dependencies') {
            steps {
                echo 'Install deps..'
                bat 'npm install'
            }
          post{ 
          success{
             slackSend message : 'Successfully installed'
       
            }
          failure {
           slackSend message : 'Installation failed'
        }
        }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'npm test'
            }
          post{ 
          success{
             slackSend message : 'Successfully tested'
       
            }
          failure {
           slackSend message : 'Testing failed'
        }
        }
        }
        stage('Package') {
            steps {
                echo 'npm build'
            }
          post{ 
          success{
             slackSend message : 'Successfully build'
       
            }
          failure {
           slackSend message : 'Building failed'
        }
        }
        }
    }
}
