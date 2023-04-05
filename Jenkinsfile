node {
    def resultImage
    def voteImage
    def workerImage
    docker.withRegistry("jenkins", "" ) { 
      stage('Clone repo') {
        checkout scm
      }
      stage('Build result') {
        resultImage = docker.build("jenkins:5000/examplevotingapp-result", "./result")
      } 
      stage('Build vote') {
        voteImage = docker.build("jenkins:5000/examplevotingapp-vote", "./vote")
      }
      stage('Build worker dotnet') {
        workerImage = docker.build("jenkins:5000/examplevotingapp-worker", "./worker")
      }
      stage('Push result image') {
          resultImage.push("${env.BUILD_NUMBER}")
          resultImage.push()
      }
      stage('Push vote image') {
          voteImage.push("${env.BUILD_NUMBER}")
          voteImage.push()
      }
      stage('Push worker image') {
          workerImage.push("${env.BUILD_NUMBER}")
          workerImage.push()
      }
    }
}
