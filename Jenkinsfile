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
        stage("Supprimer le contenu du dossier target") {
            steps {
                script {
                    //this step attempts to clean the files and directories generated by Maven during its build
                    sh "mvn clean"
                }
            }
        stage ("Creation du livrable"){
			steps{
				sh "mvn package -DskipTests=true"
			}
		}
        }

	
        	
    }
}
