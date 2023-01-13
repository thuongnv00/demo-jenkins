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
				withDockerRegistry(credentialsId: 'docker-hub', url: 'https://hub.docker.com/') {
				sh 'docker build -t kenshinthuong/demo_jenkins_docker:v1 .'
				sh 'docker push kenshinthuong/demo_jenkins_docker:v1'
				
				}
			}
		}
	}
}
