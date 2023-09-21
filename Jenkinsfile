pipeline {
    agent any 
        parameters {
            string(defaultValue: "123", description: 'This is a VM name', name: 'VM_Name')
            }
            stages {
            stage('Unstash VM_Name') {
            steps {
                unstash 'vm-name-stash'
            }
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [[$class: 'StringParameterValue', name: 'VM_Name', value: "${VM_Name}", description: 'develop-stack']];
                        //[string(name: 'VM_Name', value:  String.valueOf(VM_Name))]
                        //echo "build job: DG11-InfraOps/OTE/app-2nd-proj"
                        
                        }
                }
            }
  
}
