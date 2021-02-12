pipeline
{
  agent any
  environment{
          PATH = "/opt/maven/apache-maven-3.6.3/bin:$PATH"
      }
    stages
	{
	steps{
	stage('SCM GitCheckout'){
		    git credentialsId: '3dd0fa55-769d-4326-af17-46c823c096ee', url: 'https://github.com/jampa-rambabu/Dockerwebapp1.git'
		    }
		   }
		   steps{
		stage('maven test'){
		sh "$mvnHome/bin/mvn --version"
		sh "$mvnHome/bin/mvn clean test surefire-report:report"
		 }
	}
	}
}