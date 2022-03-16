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
                bat '''
                git add *
                git commit -m "Trying"
                git push origin master 
                '''
                
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
