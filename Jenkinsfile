pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=adetechapp -Dsonar.organization=adetechapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=1e3f6c3f480cce51a6f8a3e8b55de191b817829f'
			}
    }

	// stage('RunSCAAnalysisUsingSnyk') {
  //           steps {		
	// 			withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
	// 				sh 'mvn snyk:test -fn'
	// 			}
	// 		}
  //   }	

// building docker image
// stage('Build') { 
//             steps { 
//                withDockerRegistry([credentialsId: "dockerlogin", url: ""]) {
//                  script{
//                  app =  docker.build("tech365image")
//                  }
//                }
//             }
//     }

	// stage('Push') {
  //           steps {
  //               script{
			
  //                   docker.withRegistry("https://924338258393.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials") 
	// 		{
  //                   app.push("latest")
  //                   }
  //               }
  //           }
  //   	}


  }
}
