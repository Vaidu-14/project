pipeline{
    agent{
	label{
	     label "built-in"
		 customWorkspace "/root/project"
		}
	}
	tools {
	    maven "maven"
	}
	stages {
	    stage ("clean repo") {
		    steps {
			    sh "rm -rf /root/.m2/repository"
			}
		}
         
        	stage ("clean mvn") {
		    steps {
			    sh "mvn clean install"
			}
		}

            stage ("copy war") {
		    steps {
			    sh "cp /root/project/target/LoginWebApp.war /root/tomcat/webapps"
			}
		}	 
	}
}
