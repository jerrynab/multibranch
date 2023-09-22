pipeline {
    agent any

    stages {
        stage('Print Activity ID') {
            steps {
                script {
                    def activityID = '2023_Patch_WU'
                    echo "activityID = ${activityID}"
                }
            }
        }
    
        
               stage('Trigger Second Jenkinsfile') {
                   steps {  echo "Parent Pipeline - Triggering Child Pipeline"
                        build job: "../javawebproject/master", wait: true, parameters [string(name: 'ACTIVITY_ID', value: ACTIVITY_ID)]
                        }
                }
            }
    
}


