pipeline{
  environment{
    reg = "tarunk25/poee"
    regCre = "docker_id"
    dockerImg = ""
  }
  agent any
  stages{
    stage('Build Image'){
      steps{
        script{
          dockerImg = docker.build reg + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy the image'){
      steps{
        script{
          docker.withRegistry('',regCre){
            dockerImg.push()
          }
        }
      }
    }
  }
}
