pipeline {
    agent any
    tools{
        maven 'localMaven'
    }
    stages {
        stage('Build') {
            steps {
				echo 'Now Building...'
                call 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        
    }
}