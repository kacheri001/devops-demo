pipeline {
	agent any
	
	stages {
	  stage('Clone Code') {
		steps {
		git 'git@github.com:kacheri001/devops-pipeline-demo.git'
	}
	}
	
	stage('Build Docker Image') {
	  steps {
		script {
		dockerImage = docker.build("basha70133/devops-demo:latest")
	}
	}
	}

	stage('push to Docker Hub') {
	  steps {
	   withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
		dockerImage.push()
	}
	}
	}
	}
	}				
