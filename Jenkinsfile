pipeline{
  agent { 
    docker {
    image 'maven:3-alpine'
    args '-v /opt/tomcat/.m2:/opt/tomcat/.m2'
    } 
  }
  stages{
    stage('Build'){
      steps{
        sh 'mvn -DskipTests -B clean package'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
      post{
        always{
	  junit 'target/surefire-reports/*.xml'
	}
      }
    }
    stage('Sanity check'){
      steps{
        input "Can I deploy ?"
      }
    }
    stage('Deliver'){
      steps{
        sh 'jenkins/scripts/deliver.sh'
      }
    }
  }
  post{
    always{
      deleteDir()
    }
  }
}
