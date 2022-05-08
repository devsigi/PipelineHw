pipeline{
	agent {
		label 'mvnNode'
		/* docker{				// docker should have installed in remote server
			image 'maven:3.5.3-jdk-10-slim'
					args '-e env=Dev' // at end the container would be stopped & removed
					alwaysPull true // to pull the image latest, though there is already a local image
		} */
	}
	/* triggers{
		cron('0 2 2 3 1-7') //to run the job march 2nd at 2'o clock
		//cron('@daily')	// symbolic parms
		//pollSCM('* * * * *') // or we can poll the git for any changes
		// upstream(upstreamProjects: 'pipeline-triggers-oustream-job1, pipeline-triggers-upstream-job2',
		   threshold: hudson.model.Result.SUCCESS) //UNSTABLE, FAILURE, NOT_BUILT, ABORTED
	} */
	environment{
		env='Dev'
	}
	options{
		buildDiscarder(logRotator(numToKeepStr: '1'))
	}
	//paramaters{ string(name:env, defaultValue:'Dev', description: 'Environment to build')} run by default values, we can do Build with Parameter to accept run time inputs
	stages{
		/* stage{ agent none(=JenNode) steps{ code to pull the git code}}
		/* stage{ agent mvnNode steps{ code to build the artifact}}
		stage("Say Hai!"){
			when {
				environment name: "env", value: 'Dev'
			}
			/* when allOf {			//if there are multiple variables need to check on condition
				environment name: "env", value: 'Dev'
				environment name: "var2", value: 'value of var2'
				branch 'main'	// to run only when git is from main branch
				branch 'Prod'	// to run only when git is from Production branch
			} */
			/* input{
				message "please specify inputs"
				ok "OK"
					submitter "Dev, Admin"
					submitterParameter "whiIsSubmitter"
				//paramaters{ string(name:env, defaultValue:'Dev', description: 'Environment to build')} to accept run time inputs
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
