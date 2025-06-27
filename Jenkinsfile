pipeline {
  agent any
  tools { 
        maven 'Maven_3_2_5'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggyweb-app -Dsonar.organization=asgbuggyweb-app -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=${{ secrets.SONAR_TOKEN }}'
			}
        } 
  }
}
