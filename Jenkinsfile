pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS - credentials('f89b0d95-5f9e-4869-bea3-734b58c5d9cd')
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag jishnujoshy/pythonapp .'
            }
        }
        stage('Login to dockerhub') {
            steps {
                sh 'docker login'
            }
        }
        stage('push image') {
            steps {
                sh 'docker push jishnujoshy/pythonapp'
            }
        }
    }
}

