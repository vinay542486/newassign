pipeline{
	agent any
	
	stages{
		stage("DOCKER BUILD"){
			steps{
				echo "BUILD stage"
				sh ''' 
					cd /var/lib/jenkins/workspace/newassign
					docker build -t vinay542486/new:1.0 .
				'''
			}
		}
		stage("DOCKER PUSH"){
	                 steps{
				sh 'docker image ls'
				sh 'docker push vinay542486/new:1.0'
				echo "Docker image pushed to docker hub successfuly"
			}
		}
		
		stage("Docker-run"){
			steps{
				echo "Running container"
				sh 'docker run -it -d -p 8060:8080 --name vinay-tomcat vinay542486/new:1.0'
				
			}
		}
	}
}
