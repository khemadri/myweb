pipeline{
	agent any
	stages{
		stage("SCM checkout"){
			steps{
			 git credentialsId: 'slave-ssh', url: 'https://github.com/khemadri/myweb'
			}
		}
		stage("maven build"){
			steps{
			sh "mvn clean package"
			}
		}
	}
}
		
