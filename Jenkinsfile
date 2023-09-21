pipeline {
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '1234!'     }
            stages {
                stage('Example') {             steps {                 script {                     // Set the global environment variable                   
            env.activityID = 'my-value1'                   
            echo "Set activityID to ${env.activityID}"                 }           
                                             }
                         }
        
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'activityID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
  
}

