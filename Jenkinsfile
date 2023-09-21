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
                    
                    // Replace ACTIVITY_ID_PLACEHOLDER with the actual value
                    childPipelineScript = childPipelineScript.replace("ACTIVITY_ID_PLACEHOLDER", "${ACTIVITY_ID}")
                    
                    def childJob = load(childPipelineScript)
                    if (childJob.resultIsBetterOrEqualTo(hudson.model.Result.SUCCESS)) {
                        currentBuild.result = 'SUCCESS'
                    } else


