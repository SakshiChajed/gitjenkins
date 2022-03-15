pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo 'Build App' 
                bat '''
                date
                java -version
                '''
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
