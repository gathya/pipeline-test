
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'mvn clean package'
            }
        }
         stage('Print') {
            steps {
                echo "${readMavenPom().getProperties().get("project.build.sourceEncoding")}"
            }
        }
    }
    
}

