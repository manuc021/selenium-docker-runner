pipeline {
	agent any
	stages{
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
			archiveArtifacts artifacts: "C:\\Users\\MANU\\eclipse-workspace\\output\\**"
			bat "docker-compose down"
		}
	}
}
