pipeline{
	agent any
	stages{
		stage('Source'){
			steps{
				echo "sampath Compiled successfully"
			      	echo "Environment Selected = ${Target_Environment}"
		    		echo "Deployment Selected = ${Deploy_Method}"
				echo "WorkingWorking = ${env.WORKSPACE}"
				
				// script{
				// 	bat git --version
				// 	bat commit_ID = git rev-parse HEAD
				// 	echo "Commit ID is = ${commit_ID}"
				// }
				script {
			      if ( Target_Environment == 'iDev') {
				      echo "YEss Environment Selected = ${Target_Environment}"				      
			      }else if( Target_Environment == 'QA' ){
				      echo "YEss Environment Selected = ${Target_Environment}"			      
				}else if( Target_Environment == 'UAT' ){
				      echo "YEss Environment Selected = ${Target_Environment}"
				}
			     }
			}
		}
		stage('Sam-Checkout'){
			steps{
				git branch: "${Target_Environment}", credentialsId: 'Sam-GIT', url: 'https://github.com/sampathmsrit/Trail.git'
			}
		}
		stage('Build'){
			steps{
				echo "Qulaity successfully"
			}
				}
		stage('Win Commands'){
			steps{echo "Win Commands Execution test"
			      echo "Getting parameteres"
			      echo "===================="
			      echo "Present Commit ID = ${env.GIT_COMMIT}"
			      echo "Last success build Commit ID = ${env.GIT_COMMIT}"
			      echo "Branch = ${env.GIT_BRANCH}"
			      script{
				// bat git --version
				      bat label: '', script: 'dir'
				      bat label: '', script: 'git --version'
				      
			      }
			      
			}
		}
		stage('Final'){
			environment{
				samID = credentials('samID')
			}
			steps{
				echo "Qulaity successfully"
				echo "$samID_USR"
				echo "$samID_PSW"
			}
				}

		
		// stage("Interactive_Input") {
  //           steps {
  //               script {
  //               def userInput = input(
  //                id: 'userInput', message: 'Enter path of test reports:?', 
  //                parameters: [
  //                [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Path of config file', name: 'Config'],
  //                [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Test Info file', name: 'Test']
  //               ])
  //               echo ("IQA Sheet Path: "+userInput['Config'])
  //               echo ("Test Info file path: "+userInput['Test'])
                              
  //               }
  //           }
  //       }
		//  stage("foo") {
  //           steps {
		//     echo "Before"
  //               script {
  //                   env.RELEASE_SCOPE = input message: 'User input required', ok: 'Release!',
  //                           parameters: [choice(name: 'RELEASE_SCOPE', choices: 'patch\nminor\nmajor', description: 'What is the release scope?')]
		// 	parameters: [choice(name: 'Environement', choices: 'iDev\nQA\nUAT', description: 'What is the Env?')]
		// 	parameters: [choice(name: 'Deploy-Method', choices: 'Validate\nDeploy', description: 'What is deploy method?')]
  //               }
		//     echo "After"
  //               echo "${env.RELEASE_SCOPE}"


		    
  //           }
  //       }
		}
	}
