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
	stage ('Pull') {
	  steps {
	    bat 'docker login -u sid2104 -p BaPP4082#@Y docker.io'
        bat 'docker pull sid2104/dockerhub:docker-hello'
      }
   	  
	}
	stage ('Run') {
	  steps {
	    bat 'docker login -u sid2104 -p BaPP4082#@Y docker.io'
		bat 'docker run -d --name=using-Jenkins -p 8000:8000 sid2104/dockerhub:docker-hello'
	   }
	}
}
}
