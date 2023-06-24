pipeline {
    agent any

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
        stage ("Lancement des Tests Unitaires"){
		steps{
			sh "mvn test"
				}
		}
    }
}

