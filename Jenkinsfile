pipeline {
    agent any
    environment {
        ACTIVITY_ID = '1234!'
    }
    stages {
        stage('Trigger Second Jenkinsfile') {
            steps {
                script {
                    def childJob = build(job: '../javawebproject/master', parameters: [
                        string(name: 'ACTIVITY_ID', value: "${ACTIVITY_ID}")
                    ])
                    currentBuild.result = childJob.result
                }
            }
        }
    }
}
