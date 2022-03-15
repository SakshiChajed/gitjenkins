pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo 'Build App' 
                git 'https://github.com/SakshiChajed/gitjenkins.git'
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
