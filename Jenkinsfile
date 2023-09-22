pipeline {
    agent any

    environment {
        ACTIVITY_ID = '2023_Patch_WU'
    }

    stages {
        stage('Print Activity ID') {
            steps {
                script {
                    echo "activityID = ${ACTIVITY_ID}"
                }
            }
        }
    }
    
        
               stage('Trigger Second Jenkinsfile') {
                   steps {  echo "Parent Pipeline - Triggering Child Pipeline"
                        build job: "../javawebproject/master", wait: true, parameters [string(name: 'ACTIVITY_ID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
    
}


