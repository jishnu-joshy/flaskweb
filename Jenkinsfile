pipeline {
    agent any
    environent {
        DOCKERHUB_CREDENTIALS - credentials('dckr_pat__FrZsbuNomi4XDQqNxo3UNvKghw')
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

