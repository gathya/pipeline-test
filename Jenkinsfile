
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
         stage('Print') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "${readMavenPom().getProperties().get("project.build.sourceEncoding")}"
            }
        }
    }
    
}

