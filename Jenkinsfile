pipeline {
    agent any
    environment {
        ACTIVITY_ID = '1234!'
    }
    stages {
        stage('Trigger Second Jenkinsfile') {
            steps {
                script {
                    def childJob = build(job: '../javawebproject/master')
                    childJob = childJob.waitForCompletion()
                    if (childJob.resultIsBetterOrEqualTo(Result.SUCCESS)) {
                        currentBuild.result = 'SUCCESS'
                    } else {
                        currentBuild.result = 'FAILURE'
                    }
                }
            }
        }
    }
}
