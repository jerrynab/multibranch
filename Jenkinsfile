pipeline {
    agent any
    environment {
        ACTIVITY_ID = '1234!'
    }
    stages {
        stage('Trigger Second Jenkinsfile') {
            steps {
                script {
                    def childPipelineScript = readFileFromWorkspace('../javawebproject/master/Jenkinsfile')
                    childPipelineScript = childPipelineScript.replace("ACTIVITY_ID_PLACEHOLDER", "${ACTIVITY_ID}")
                    
                    def childJob = evaluate(childPipelineScript)
                    if (childJob.resultIsBetterOrEqualTo(hudson.model.Result.SUCCESS)) {
                        currentBuild.result = 'SUCCESS'
                    } else {
                        currentBuild.result = 'FAILURE'
                    }
                }
            }
        }
    }
}

