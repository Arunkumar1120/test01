pipeline{
	agent any 
        parameters {
           	 choice(name: 'BranchName', choices:['main','branch01','branch02'], description: 'to refresh the list, go to configure, disable "this build has parameters", launch build (without parameters)to reload the list and stop it, then launch it again (with parameters)')
	}
	
	stages{
 
		stage('Checkout') {
			steps{
				git branch: 'main', credentialsId: '9c2554ea-60d2-4fc7-8612-fb72139b3b89', url: 'https://github.com/manojsubramaniam/test01.git'
   		
			}
		}
					
		stage("build docker image"){
		     	steps {
				
				sh '''
					docker build -t nginx/nodeapp_test:latest .
					docker run -d --name nginx123 -p 8000:80 nginx/nodeapp_test:latest
				'''
			}
		}

		stage("docker container"){
			steps {
				echo'running docker image into container..'
			}
		}
	
	}
}
