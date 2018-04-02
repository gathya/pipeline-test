
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
         stage('Print') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                PROJ_BASE_NAME = "${readMavenPom().getProperties().get("project.build.sourceEncoding")}/${readMavenPom().getArtifactId()}"
                echo "Project name ${PROJ_BASE_NAME}"
            }
        }
    }
    
}

