pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('d373911e-8378-420d-b805-2764eea15abf')
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag jishnujoshy/pythonapp .'
            }
        }
        stage('Login to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push image') {
            steps {
                sh 'docker push jishnujoshy/pythonapp'
            }
        }
    }
}

