pipeline{
  agent { 
    docker {
    image 'maven:3-alpine'
    args '-v /opt/tomcat/.m2:/opt/tomcat/.m2'
    } 
  }
  stages{
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn -B clean package'
      }
    }
  }
}
