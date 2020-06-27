pipeline {
    agent any
    
    stages {
        stage('Build'){
            steps{
                echo 'Building or Resolve dependencies!'
                sh 'bundle install'
            }
        }
        
        stage('Test'){
            steps{
                echo 'Running Regression Tests'
            }
        }
        
        stage('UAT'){
            
            steps{
                echo 'Wait for User Acceptance '
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        
        stage('Prod'){
            steps{
                echo 'Web app is ready :)'
            }
        }
    }
}