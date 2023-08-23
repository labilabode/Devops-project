pipeline {
  agent any
  tools { 
        maven 'maven-3-5-2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=classdev -Dsonar.organization=classdev -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=72403336afc456285e92399ce0be924a6bc61e26'
			}
    }
  
	// stage('RunSCAAnalysisUsingSnyk') {
  //           steps {		
	// 			withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
	// 				sh 'mvn snyk:test -fn'
	// 			}
	// 		}
  //   }	


//building docker image
// stage('Build') { 
//             steps { 
//                withDockerRegistry([credentialsId: "dockerlogin", url: ""]) {
//                  script{
//                  app =  docker.build("adegokeimage")
//                  }
//                }
//             }
//     }

	// stage('Push') {
  //           steps {
  //               script{
			
  //                   docker.withRegistry("https://585943330578.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials") 
	// 		{
  //                   app.push("latest")
  //                   }
  //               }
  //           }
  //   	}


  }
}
