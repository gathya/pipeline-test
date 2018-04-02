pipeline {

    agent any

    environment {

      PROJ_BASE_NAME = "${readMavenPom().getProperties().get("project.build.sourceEncoding")}/${readMavenPom().getArtifactId()}"

      PROJ_TAG = "${readMavenPom().getVersion()}"

      IMAGE_LOCAL_NAME = "${IMAGE_BASE_NAME}:${IMAGE_TAG}"

      IMAGE_FULL_NAME = "${ARTIFACTORY_URL}/${IMAGE_LOCAL_NAME}"

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

                              color: 'good',

                              message: "The pipeline [${currentBuild.fullDisplayName}] back to normal."

                }

            }

        }

        failure {

                      color: 'danger',

                      message: "The pipeline [${currentBuild.fullDisplayName}] failed."

        }

               }

}
