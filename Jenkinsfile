pipeline{
	agent {
		label 'mvnNode'
	}
	environment{
		env='Dev'
	}
	stages{
		stage("Say Hai!"){
			when {
				environment name: "env", value: 'Dev'
			}
			/* when allOf {			//if there are multiple variables need to check on condition
				environment name: "env", value: 'Dev'
				environment name: "var2", value: 'value of var2'
			} */
			steps{
				echo "Hellow world!"
				sleep(2)
			}
		}
		stage("Fetch the code"){
			when {
				environment name: "env", value: 'Dev'
			}			
			steps{
				echo "Fetched the code"
				sleep(2)
			}
		}
		stage("Build the artifact"){
			when {
				environment name: "env", value: 'Prod'
			}			
			steps{
				/* retry(3){ echo "code we want to try for 3 times" } */
				echo "Artifact is ready"
				sleep(2)
			}
		}
		stage("Deploy the artifact"){
			when {
				environment name: "env", value: 'Prod'
			}			
			steps{
				echo "Deployed the artifact"
				sleep(2)
			}
		}
	}
}
