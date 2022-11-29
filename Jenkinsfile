pipeline{
	agent any
	tools {
            maven 'maven2'
                }
	stages{
// 		stage("SCM checkout"){
// 			steps{
// 			git credentialsId: 'khemadri', url: 'https://github.com/khemadri/myweb'
// 			}
// 		}
		stage("maven build"){
			steps{
			 sh "mvn package"
			}
		}
		stage("deploy to tomcat"){
			steps{
		            sshagent(['tomcat-dev']) {
		             sh "mv target/*.war target/webapp.war"		    
                             sh "scp -o StrictHostKeyChecking=no target/webapp.war ec2-user@172.31.35.101:/opt/tomcat9/webapps/"
			     sh "ssh ec2-user@172.31.35.101 /opt/tomcat/bin/shutdown.sh"	
			      sh "ssh ec2-user@172.31.35.101 /opt/tomcat/bin/startup.sh"		    
               }
	}
    }
 }
}
		
