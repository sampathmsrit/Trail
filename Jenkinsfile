pipeline{
	agent any
	stages{
		stage('Source'){
			steps{echo "sampath Compiled successfully"
			}
				}
		stage('Build'){
			steps{echo "Qulaity successfully"}
				}
		stage("Interactive_Input") {
            steps {
                script {
                def userInput = input(
                 id: 'userInput', message: 'Enter path of test reports:?', 
                 parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Path of config file', name: 'Config'],
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Test Info file', name: 'Test']
                ])
                echo ("IQA Sheet Path: "+userInput['Config'])
                echo ("Test Info file path: "+userInput['Test'])
                              
                }
            }
        }
		 stage("foo") {
            steps {
		    echo "Before"
                script {
                    env.RELEASE_SCOPE = input message: 'User input required', ok: 'Release!',
                            parameters: [choice(name: 'RELEASE_SCOPE', choices: 'patch\nminor\nmajor', description: 'What is the release scope?')]
			parameters: [choice(name: 'Environement', choices: 'iDev\nQA\nUAT', description: 'What is the Env?')]
			parameters: [choice(name: 'Deploy-Method', choices: 'Validate\nDeploy', description: 'What is deploy method?')]
                }
		    echo "After"
                echo "${env.RELEASE_SCOPE}"
		    echo "Environment Selected = ${Target_Environment}"
		    echo "Deployment Selected = ${Deploy_Method}"

		    
            }
        }
		}
	}
