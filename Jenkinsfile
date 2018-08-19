pipeline{
  agent { 
    docker {
    image 'maven:3-alpine'
    } 
  }
  stages{
    stage('Build'){
      steps{
        mvn clean package
      }
    }
  }
}
