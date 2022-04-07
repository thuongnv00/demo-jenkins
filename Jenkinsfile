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
			echo 'Success ...............................'
				withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
				sh 'docker build -t kenshinthuong/demo_jenkins_docker:v1 .'
				sh 'docker push kenshinthuong/demo_jenkins_docker:v1'
				
				}
			}
		}
		stage('Run container in Kubernetes') {
			steps{
				echo 'Kubernetes ...............................'
				script {
					kubernetesDeploy(configs: "bwce_jenkins.yaml",kubeconfigId:"kubernetes")
				}
			}
		}
		
	
	}
}