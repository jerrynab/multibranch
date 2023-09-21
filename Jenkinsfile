pipeline {
    agent any

    environment {
        ACTIVITY_ID = '2023_Patch_WU'
    }

    stages {
        stage('Print Environment Variable') {
            steps {
                script {
                    echo "Parent Pipeline - ACTIVITY_ID = ${ACTIVITY_ID}"
                }
            }
        }
    }
               stage('Trigger Second Jenkinsfile') {
                   steps {
                        build job: "../javawebproject/master", wait: true, 
                        }
                }
            }
  


