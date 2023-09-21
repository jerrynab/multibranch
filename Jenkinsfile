pipeline {
    agent any 
        parameters {
            string(defaultValue: "123", description: 'This is a VM name', name: 'VM_Name')
            }
            stages {
        stage('Create File') {
            steps {
                sh 'echo "Hello, World!" > my-file.txt'
                archiveArtifacts artifacts: 'my-file.txt', allowEmptyArchive: true
            }
        }
        }
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true;
                        
                        }
                }
            }
  

