pipeline {
    agent any

    stages {
        stage('Set Activity ID') {
            steps {
                script {
                    def activityID = '2023_Patch_WU'
                    stash includes: 'activityID.txt', name: 'activityID'
                    echo "Parent Pipeline - Stashed activityID = ${activityID}"
                }
            }
        }
        stage('Print Stashed Activity ID') {
            steps {
                script {
                    def stashedActivityID = readFile('activityID.txt').trim()
                    echo "Parent Pipeline - Retrieved stashed activityID = ${stashedActivityID}"
                }
            }
        }
               stage('Trigger Second Jenkinsfile') {
                   steps {
                        build job: "../javawebproject/master", wait: true
                        }
                }
            }
  


