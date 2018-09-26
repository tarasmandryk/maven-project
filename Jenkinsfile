pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'				
            }
            post {
                success {
                    /* echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war' */
					echo 'Building docker image...'
					bat "docker build . -t tomcatwebapp:${env.BUILD_ID}"
                }
            }
        }
    }
}