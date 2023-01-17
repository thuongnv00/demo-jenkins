pipeline {
	agent any
	stages {
		stage('Clone git') {
			steps{
				git branch: 'master', url: 'https://github.com/thuongnv00/demo-jenkins.git'
			}
		}
		stage('Docker build and push') {
			steps{
			echo "PATH is: $PATH"
				withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {

				sh 'docker ps'
				
				}
			}
		}
	}
}
