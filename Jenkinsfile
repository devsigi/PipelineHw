pipeline{
	agent {
		label 'mvnNode'
	}
	stages{
		stage("Say Hai!"){
			steps{
				echo "Hellow world!"
			}
		}
		stage("Fetch the code"){
			steps{
				echo "Fetched the code"
			}
		}
		stage("Build the artifact"){
			steps{
				echo "Artifact is ready"
			}
		}
		stage("Deploy the artifact"){
			steps{
				echo "Deployed the artifact"
			}
		}
	}
}
