def ACTIVITY_ID = '2023_Patch_WU'

pipeline {
    agent any

    stages {
        stage('Print Activity ID') {
            steps {
                script {
                    echo "Parent Pipeline - ACTIVITY_ID = ${ACTIVITY_ID}"
                }
            }
        }
    
        
               stage('Trigger Second Jenkinsfile') {
                   steps { echo "Parent Pipeline - Triggering Child Pipeline"
            script {
                // Store ACTIVITY_ID in a shared variable for the child pipeline
                sharedVars = [:]
                sharedVars.ACTIVITY_ID = ACTIVITY_ID
                currentBuild.sharedVars = sharedVars
                        build job: "../javawebproject/master", wait: true
                        }
                }
            }
    }
  
}

