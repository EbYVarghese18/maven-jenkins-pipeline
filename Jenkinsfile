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
        stage('Build') {
            steps {
                echo 'Build'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
            post {
                success {
                    echo 'Finished'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver'
            }
        }
    }
}