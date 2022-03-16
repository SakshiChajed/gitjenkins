pipeline {
    agent any 
    stages {
        stage('Env Checkout') { 
            steps { 
                bat '''
                date
                java -version
                git status
                '''
            }
        }
        stage('Git') { 
            steps {
                git credentialsId: '57112c64-5128-4068-a52f-15128af17778', url: 'https://github.com/SakshiChajed/gitjenkins.git' 
               }
        }
        stage('Build') { 
            steps {
                echo 'Build App'
            }
        }
        stage('Test') { 
            steps {
                echo 'Test App' 
                
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Deploy App' 
               }
        }
        
    }
    
     post {
       always 
         {
            emailext body: 'Summary', subject: 'Pipeline Status', to: 'sakshichhajed30@gmail.com'
        }
    }
}
