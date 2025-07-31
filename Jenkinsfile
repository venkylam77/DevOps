pipeline {
    agent any
    tools {
        
        maven 'Maven_3.9.11' 
        jdk 'JDK 17'
        //docker 'docker'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building spring-boot-docker-image start..'
                dir('spring-boot-docker-image') {
                   echo 'running mvn clean compile command..'
                   sh 'mvn clean compile'
                    
                }
               echo 'Building spring-boot-docker-image end..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging spring-boot-docker-image start..'
                dir('spring-boot-docker-image') {
                   echo 'running mvn package command..'
                   sh 'mvn package'
                    
                }
               echo 'packaging spring-boot-docker-image end..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    stage('Docker Build') {
      //agent docker
      steps {
          echo 'Building Docker Image for spring-boot-docker-image start...'
          echo 'running docker build -t spring-boot-docker-image:latest .webhook....'
          script {
                withDockerRegistry(credentialsId: 'dockerhub', toolName: 'mydocker') {
                         sh 'docker build -t venkylam77/spring-boot-docker-image:latest .'
                         sh 'docker push'
                     }
                } 
               
         echo 'Building Docker Image for spring-boot-docker-image end..'
          
      }
    }
}
}
