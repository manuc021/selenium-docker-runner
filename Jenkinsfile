pipeline {
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
			 bat "docker pull mac021/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
			 bat "docker-compose up -d hub firefox chrome"
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
