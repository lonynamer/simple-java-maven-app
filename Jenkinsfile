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
    stage('Build'){
      steps{
        sh 'mvn -B clean package'
      }
    }
    post{
      always{
        junit 'target/surefire-reports/*.xml' 
      }
    }
  }
}
