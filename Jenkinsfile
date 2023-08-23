pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=devopapp -Dsonar.organization=devopapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=54028be6c5d82fc70c6619cfaf25cdcb912bb157'
			}
    }
  
	stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    }	


//building docker image
stage('Build') { 
            steps { 
               withDockerRegistry([credentialsId: "dockerlogin", url: ""]) {
                 script{
                 app =  docker.build("adegokeimage")
                 }
               }
            }
    }

	stage('Push') {
            steps {
                script{
			
                    docker.withRegistry("https://585943330578.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials") 
			{
                    app.push("latest")
                    }
                }
            }
    	}


  }
}
