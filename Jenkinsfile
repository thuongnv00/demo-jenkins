pipeline {
	agent any
	stages {
		stage('Clone git') {
			steps{
				git branch: 'main', url: 'https://github.com/thuongnv00/demo-jenkins.git'
			}
		}
		stage('Docker build and push') {
			steps{
			echo 'Success ...............................'
				withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
				sh 'docker build -t kenshinthuong/demo_jenkins_docker:v1 .'
				sh 'docker push kenshinthuong/demo_jenkins_docker:v1'
				}
			}
		}
		stage('Run container in docker') {
			steps{
				echo 'Docker ...............................'
				sh 'docker run --name demo_jenkins -p 8085:8085 -h demo kenshinthuong/demo_jenkins_docker:v1'
			}
		}
		
	
	}
}