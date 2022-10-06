pipeline{
  agent any
  stages{
    stage(“Git Checkout”){
      steps{
          git credentialsId: 'e5d7f05e-b5db-4c5a-a85e-0af76ee5cfd1', url: 'https://github.com/jishnu-joshy/flaskweb.git'
      }
    }
  }
}
