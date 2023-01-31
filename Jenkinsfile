pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
        stage('Build Maven') {
            steps {
                echo 'Build Maven starts'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/EbYVarghese18/maven-jenkins-pipeline']])
                sh 'mvn clean install'
                echo 'Build Maven Ends'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Build Dockerimage starts'
                script{
                    sh 'docker build -t ebyvarghese18/my-app-1.0-SNAPSHOT:1.0 .'
                }
            }
        }
        stage('Push Docker image to Dockerhub') {
            steps {
                echo 'Deliver'
            }
        }
    }
}