pipeline {
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '1234!'     }
            stages {
        
        
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'activityID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
  
}
