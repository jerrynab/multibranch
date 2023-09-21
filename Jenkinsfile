
pipeline {
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '2023_Patch_WU'    }
            stages {
               
        stage('Use activityID in Job') {           
            steps {         script{         echo 'Received activityID: ${activityID}'                // Use VM_Name in your job as needed                      
    }
}
        }
               stage('Trigger Second Jenkinsfile') {
                   steps {
                        build job: "../javawebproject/master", wait: true, 
                        }
                }
            }
  
}

