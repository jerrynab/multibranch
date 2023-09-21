groovyCopy code@Library('globalvarhelper')
pipeline {@Library('globalvarhelper')
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '1234!'     }
            stages {
                stage('Example') {             steps {  
                    org.mycompany.JenkinsUtils.createGlobalEnvironmentVariables('activityID1', 121212154')
                                             }
                         }
        stage('Use activityID in Job') {           
            steps {                 sh "echo 'Received activityID: ${env.activityID1}'"                 // Use VM_Name in your job as needed                      
    }
}
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'activityID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
  
}

