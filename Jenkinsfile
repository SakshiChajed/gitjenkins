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
                script{
                git credentialsId: '57112c64-5128-4068-a52f-15128af17778', url: 'https://github.com/SakshiChajed/gitjenkins.git'
                bat '''
                dir
                git branch -a
                git checkout master
                '''
               }
            }
        }
        stage('Push File to Git') { 
            steps {
                bat '''
                git status
                git add .
                git commit -m "Commit the modified file"
                git push origin master
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
