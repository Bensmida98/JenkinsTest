pipeline {

    agent any
   // triggers {
     // cron('*/4 * * * *')

//    } 

    stages {
        stage ('GIT') {
             steps {
                echo "Getting Project from Git"; 
                git branch:"master", url : "https://github.com/haifgh/Devops-gomycode.git"; 
             }
          }

       stage("Verification du version Maven") {
           steps {
                sh "mvn -version"
              
            }
        }
	
        	
    }
}
