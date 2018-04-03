
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
         stage('Print') {
            steps {
                echo "${readMavenPom().getProperties().get("project.build.sourceEncoding")}"
            }
        }
    }
    
}

