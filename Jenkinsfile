pipeline {
    agent any

  
 parameters {
    string(name: 'ACTIVITY_ID', defaultValue: "1234!")}
    stages {        
               stage('Trigger Second Jenkinsfile') {
                   steps { script{  echo "Parent Pipeline - Triggering Child Pipeline"
                        //def childPipeline = build job: 'child_pipeline', wait: true 
                        build(job: "master/javawebproject", wait: true, parameters: [string(name: 'ACTIVITY_ID', value: "${ACTIVITY_ID}")])
                        // parameters: [string(name: 'ACTIVITY_ID', value: "${params.ACTIVITY_ID}")]

                        }
                }
            }
    }
    
}
