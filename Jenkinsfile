pipeline {
    agent any
    environment {
        // This can be nexus3 or nexus2
        NEXUS_VERSION = "nexus3"
        // This can be http or https
        NEXUS_PROTOCOL = "http"
        // Where your Nexus is running
        NEXUS_URL = "localhost:8081/Nexus"
        // Repository where we will upload the artifact
        NEXUS_REPOSITORY = "Releases"
        // Jenkins credential id to authenticate to Nexus OSS
        NEXUS_CREDENTIAL_ID = "admin:admin123"
    }
	
    stages {
        stage ('GIT') {
            steps {
                echo "Getting Project from Git"
                git branch: 'master', url: 'https://github.com/Bensmida98/JenkinsTest.git'
            }
        }

        stage('Verification du version Maven') {
            steps {
                sh 'mvn -version'
            }
        }

        stage('Supprimer le contenu du dossier target') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Creation du livrable') {
            steps {
                sh 'mvn package -DskipTests=true'
            }
        }
	stage("Deploiement dans nexus ") {
     		 steps{
                          }
  			sh "mvn deploy -DskipTests=true"
                }    
	    	    
}

