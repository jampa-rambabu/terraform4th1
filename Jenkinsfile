pipeline
{
  agent any
  environment{
          PATH = "/opt/maven/apache-maven-3.6.3/bin:$PATH"
      }
    stages
	{
	stage('SCM GitCheckout'){
		    try{
		    git credentialsId: '3dd0fa55-769d-4326-af17-46c823c096ee', url: 'https://github.com/jampa-rambabu/Dockerwebapp1.git'
		    }catch(err){
		    sh "echo error in checkout"
		   }
		}
		stage('maven test'){
		try{
		mvnHome=tool 'maven-3.6.3'
		sh "$mvnHome/bin/mvn --version"
		sh "$mvnHome/bin/mvn clean test surefire-report:report"
		}
		catch(err){
		sh "echo error defining maven"
		}
		}
	}
}