pipeline {
	agent any
	stages {
		stage('Clone git') {
			steps{
				git branch: 'master', url: 'https://github.com/thuongnv00/demo-jenkins.git'
			}
		}
		stage('Docker Build') {
      			steps {
      				sh 'docker build -t kenshinthuong/demo_jenkins_docker:v1 .'
     			 }
   		 }
	}
}
