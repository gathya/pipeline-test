pipeline {
    agent any
    environment {
      PROJ_BASE_NAME = "${readMavenPom().getProperties().get("project.build.sourceEncoding")}/${readMavenPom().getArtifactId()}"
      PROJ_TAG = "${readMavenPom().getVersion()}"
      message: "The pipeline [${PROJ_TAG}] version."
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
                              color: 'green',
                              message: "The pipeline [${currentBuild.fullDisplayName}] back to normal."
                }
            }
        }
        failure {
                      color: 'red',
                      message: "The pipeline [${currentBuild.fullDisplayName}] failed."
        }
               }
}
