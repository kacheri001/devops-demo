pipeline {
	agent any

	environment {
		DOCKER_IMAGE = 'kacheri001/myapp'
		}

	stages {
		stage('Build Docker Image') {
			steps {
				script {
					dockerImage = docker.build("${DOCKER_IMAGE}")
				}
			}
		}
		
		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('https://index.docker.io/v1/',dockerhub') {
						dockerImage.push()
					}
				}
			}
		}
	}
} 
