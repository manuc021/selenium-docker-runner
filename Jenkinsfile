pipeline {
	agent any
	stages{
		stage("Run Test"){
			steps{
			 bat "docker-compose up search-module book-flight-module"
			}
		}
		stage("Stop Grid"){
			steps {
			 bat "docker-compose down"
			}
		}
	}
}
