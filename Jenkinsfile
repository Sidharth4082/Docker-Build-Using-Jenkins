pipeline {
  agent any
  stages {
    stage ('Build') {
	  steps {
	    bat 'docker build -t hello-Docker .'
		}
	}
	stage ('Login') {
	  steps {
	    bat 'docker login -u sid2104 -p BaPP4082#@Y docker.io'
		}
	}
	stage ('Push') {
	  steps {
	    bat 'docker push sid2104/dockerhub:hello-docker'
		}
	}
	stage ('Pull and Deploy') {
	  steps {
	    bat 'docker run -d --name=using-jenkins -p 8000:8000 hello-Docker'
		}
	}
}
}
