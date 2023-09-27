pipeline {
    agent any


parameters {
    string(name: 'ACTIVITY_ID', defaultValue: "1234!")}
    stages {        
               stage('Trigger Second Jenkinsfile') {
                   steps {  echo "Parent Pipeline - Triggering Child Pipeline"
                         build(job: "master/javawebproject", wait: true, parameters: [string(name: 'ACTIVITY_ID', value: "${ACTIVITY_ID}")])
                        }
                }
            }
    
}


