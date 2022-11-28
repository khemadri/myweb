pipeline{
	agent any
	tools {
            maven 'maven2'
                }
// 	stages{
// 		stage("SCM checkout"){
// 			steps{
// 			git credentialsId: 'khemadri', url: 'https://github.com/khemadri/myweb'
// 			}
// 		}
		stage("maven build"){
			steps{
			sh "mvn clean package"
			}
		}
	}
}
		
