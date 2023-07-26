pipeline {
	agent any
	stages{
		stage("Start Grid"){
			steps{
			 bat "docker-compose up -d hub --scale chromenode=5"
			}
		}
		stage("Run Test"){
			steps{
			 bat "docker-compose up book-flight-module search-module"
			}
		}
	}
	post{
		always {
			archiveArtifacts artifacts: "output/**"
			bat "docker-compose down"
		}
	}
}
