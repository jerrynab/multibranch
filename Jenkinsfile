pipeline {
    agent any

    stages {
        stage('Print Activity ID') {
            steps {
                script {
                    def ACTIVITY_ID = '2023_Patch_WU'
                    echo "ACTIVITY_ID = ${ACTIVITY_ID}"
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


