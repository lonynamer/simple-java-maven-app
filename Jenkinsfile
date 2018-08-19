pipeline{
  agent { 
    docker {
    image 'maven:3-alpine'
    opts '-v /opt/tomcat/.m2:/opt/tomcat/.m2'
    } 
  }
  stages{
    stage('Test'){
      steps{
        mvn test
      }
    }
  }
}
