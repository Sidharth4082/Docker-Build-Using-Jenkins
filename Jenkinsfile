pipeline {
  agent any
  stages {
    stage ('Build') {
	  steps {
	    bat 'docker build -t python-app:v1 .'
		}
	}
	stage ('Login') {
	  steps {
	    bat 'docker login -u sid2104 -p BaPP4082#@Y docker.io'
		}
	}
	stage ('Push') {
	  steps {
	    bat 'docker tag python-app:v1 sid2104/dockerhub:docker-hello'
	    bat 'docker push sid2104/dockerhub:docker-hello'
		}
	}
	stage ('Pull and Deploy') {
	  steps {
	    bat 'docker run -d --name=using-jenkins -p 8000:8000 hello-Docker'
		}
	}
}
}
