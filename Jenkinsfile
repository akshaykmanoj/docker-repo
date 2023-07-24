pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/akshaykmanoj/docker-repo.git'
            }
        }
        stage('Maven Build') {
            steps {
                bat 'mvn clean install'
            }
            
        }
        stage('Unit Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('code analysis') {
            steps {
                withSonarQubeEnv('sonar-token') {
                    bat """
                    mvn install sonar:sonar ^
                    -Dsonar.organization=akshaykmanoj ^
                    -Dsonar.projectKey=akshaykmanoj_sonar-token ^
                    -Dsonar.host.url=https://sonarcloud.io
                    """
                }
            }
        }
        stage('Docker Login and Build') {
            steps {
                withCredentials([string(credentialsId: 'akshaykmanoj', variable: 'docker-pwd')]) {
                    bat 'docker login -u akshaykmanoj -p %docker-pwd%'
                    bat 'docker build -t docker-repo-task .'
                }
            }
        }
        
        stage('Docker Tag and Push') {
            steps {
                script {
                    def registryUrl = "docker.io"
                    def imageNameWithTag = "akshaykmanoj/docker-repo-task:${env.BUILD_NUMBER}"
                    
                    bat "docker tag docker-repo-task ${registryUrl}/${imageNameWithTag}"
                    bat "docker push ${registryUrl}/${imageNameWithTag}"
                }
            }
        }
        stage('Docker Logout') {
            steps {
                bat 'docker logout'
            }
        }
    }
}
