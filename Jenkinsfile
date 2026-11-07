pipeline {

	agent any

	environment {
		PATH = "/opt/maven/bin:$PATH"

	}

	stages {
		stage("build"){
			steps{
			  sh 'mvn clean package'	
			}
		}	
		stage('SonarQube analisis'){
			environment {
			 scannerhome = tool 'mayur-sonar-scanner'	
}
			steps{
			 withSonarQubeEnv('mayur-sonarqube-server'){
				sh "${scannerHOME}/bin/sonar-scanner"	
			
				}
			}
		}

	}
}
