pipeline{
	agent any
	parameters {
		string(name: 'Project', defaultValue: 'sample project tuesday', description: 'sample project for today')
		choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'select the version')
	}

	stages{

		stage("build"){

			steps {
				echo'building the appilication..'
				echo"building version ${NEW_VERSION}"
			}
		}
		stage("test"){
		     	steps {
				echo'testing the appilication..'
			}
		}

		stage("deploy"){
			steps {
				echo'deploying the appilication..'
				echo"deploying version ${VERSION}"
			}
		}
	}
}
