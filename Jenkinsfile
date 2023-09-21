groovyCopy code@Library('globalvarhelper')
pipeline {@Library('globalvarhelper')
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '1234!'     }
            stages {
                stage('Example') {             steps {  
                    org.mycompany.JenkinsUtils.createGlobalEnvironmentVariables("activityID", "121212154")
                                             }
                         }
        
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'activityID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
  
}

