pipeline {
    agent {        
        docker{
            //image 'qaninja/rubywd'
            //TESTAR COM IMAGEM QUE SUBI NO MEU WORKSPACE
            image 'regisalexandria/rubywd'
        }
    }
    
    stages {
        stage('Build'){
            steps{
                echo 'Building or Resolve dependencies!'
                sh 'rm -f Gemfile.lock'
                sh 'bundle install'
            }
        }
        
        stage('Test'){
            steps{
                echo 'Running Regression Tests'                
                sh 'bundle exec cucumber -p ci'
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