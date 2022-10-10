pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('f89b0d95-5f9e-4869-bea3-734b58c5d9cd')
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
         stage('Deploying the appto kubernetes') {
             steps {
                 script {
                     kubernetesDeploy(configs: "deployment.yml", kubeconfigId:| "ff0a77db-1962-46a3-95f5-5ed6a0a246f8")
                 }
             }
         }
    }
}

