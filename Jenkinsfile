pipeline {
    agent any 
        parameters {
            string(defaultValue: "123", description: 'This is a VM name', name: 'VM_Name')
            }
    environment {         MY_VARIABLE = 'Hello, World!'     }
            stages {
        
        
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'VM_Name', value: "${MY_VARIABLE}")]
                        }
                }
            }
  
}
