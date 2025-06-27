pipeline {
  agent any
  tools { 
        maven 'Maven_3_2_5'  
    }
   stages{
      stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggyweb-app -Dsonar.organization=asgbuggyweb-app -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=c931a965ffedba4ec01bca51b0be67cff984ea28'
			}
        }

      stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    }
  }
}
