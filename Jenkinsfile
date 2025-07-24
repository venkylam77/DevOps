pipeline {
    agent any
    tools {
        
        maven 'Maven_3.9.11' 
        jdk 'JDK 17'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building23..'
                echo 'sh pwd1..'
                sh "pwd"
                dir('spring-boot-docker-image/src') {
                    echo 'sh pwd2..'
                   sh "pwd"
                   sh 'mvn clean compile'
                    
                }
                echo 'sh pwd3..'
               sh "pwd"
                
            
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
