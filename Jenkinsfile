pipeline
{
  agent any
  environment{
          PATH = "/opt/maven/apache-maven-3.6.3/bin:$PATH"
      }
    stages
	{
	stage('SCM GitCheckout'){
	      steps{
		    git credentialsId: '3dd0fa55-769d-4326-af17-46c823c096ee', url: 'https://github.com/jampa-rambabu/Dockerwebapp1.git'
		    }
		  }
		stage('maven test'){
		    steps{
		sh "mvn --version"
		sh "mvn clean test surefire-report:report"
		}
             }
        stage('Test Case and Reports'){
           steps{
        echo "executing the test cases"
        junit allowEmptyResults: true, testResults: '/var/lib/jenkins/workspace/Jenkins_git_maven_docker_terra_s3/target/surefire-reports/*.xml'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/Jenkins_git_maven_docker_terra_s3/target/site', reportFiles: 'surefire-report.html', reportName: 'SureFireReportsHTML', reportTitles: ''])
        }
	}
}
}