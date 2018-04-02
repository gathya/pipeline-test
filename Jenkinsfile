pipeline {
    agent any
    environment {
      PROJ_BASE_NAME = "${readMavenPom().getProperties().get("project.build.sourceEncoding")}/${readMavenPom().getArtifactId()}"
      PROJ_TAG = "${readMavenPom().getVersion()}"
    }
    stages {
        stage('Build Jar') {
            steps {
                echo "Building JAR file..."
                sh 'mvn clean package'
                echo 'JAR file sucessfully built.'
            }
        }
        }
    post {
        success {
            script {
                if (currentBuild.previousBuild?.result == 'FAILURE') {
                }
            }
        }
        failure {
        }
               }
}
