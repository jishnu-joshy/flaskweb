# flaskweb
flaskweb repo



pipeline{
  agent any
  stages{
    stage("Git Checkout"){
      steps{
        git credentialsId: 'e5d7f05e-b5db-4c5a-a85e-0af76ee5cfd1', url: 'https://github.com/jishnu-joshy/flaskweb.git'
      }
    }
  }
}


docker plugin === Docker Commons Plugin

kubernetes plugin ===== kubernets continues deployment


 [[[ stage('Deploying the appto kubernetes') {
            steps {
                script {
                    kubernetesDeploy(configs: "deployment.yml", kubeconfigId:| "ff0a77db-1962-46a3-95f5-5ed6a0a246f8")
                }
            }
        } 
        ]]]

secret ------kubectl create secret docker-registry regcred --docker-server=pythonapp --docker-username=jishnujoshy  --docker-password=sdfdghh--docker-email=jishnujoshy699@gmaiol.com -n development
