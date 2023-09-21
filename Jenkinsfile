@Library('globalvarhelper') _
import org.mycompany.SharedVariables

pipeline {
    agent any

    stages {
        stage('Print Activity ID') {
            steps {
                script {
                    def sharedVars = new SharedVariables()
                    echo "Parent Pipeline - ACTIVITY_ID = ${sharedVars.ACTIVITY_ID}"
                }
            }
        }
    }
    
        
               stage('Trigger Second Jenkinsfile') {
                   steps {  echo "Parent Pipeline - Triggering Child Pipeline"
                        build job: "../javawebproject/master", wait: true
                        }
                }
            }
    
  


