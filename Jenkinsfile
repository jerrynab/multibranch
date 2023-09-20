//properties([
//    parameters ([
//        string(defaultValue: "123", description: 'This is a VM name', name: 'VM_Name')
//        ])
//    ])
            


pipeline {
    agent any 
        parameters {
            string(defaultValue: "123", description: 'This is a VM name', name: 'VM_Name')
            }
            stages {
                stage('Preparation stage') {
                    steps {
                        echo "Hello World"
                        }
                    }
                stage ('Checkout Ansible') {
                    steps {
                        checkout([
                            $class: 'GitSCM',
                            branches: [[name: '*/master']],
                            userRemoteConfigs: [[url: 'https://dg11-gitlab.athens.intrasoft-intl.private:9084/infraops/ote-iac/ansible.git']],
                            extensions: [[$class: 'PathRestriction', excludedRegions: '', includedRegions: 'infraops/ote-iac/ansible']]
                            ])
                        }
                    }
                stage('Run Ansible Playbook') {
                    steps {
                            echo "Running ansible playbook test_playbook.yaml"
                        }
                    }
                stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "DG11-InfraOps/OTE/patch_management/master", wait: true, parameters: [[$class: 'StringParameterValue', name: 'VM_Name', value: "${VM_Name}", description: 'develop-stack']];
                        //[string(name: 'VM_Name', value:  String.valueOf(VM_Name))]
                        //echo "build job: DG11-InfraOps/OTE/app-2nd-proj"
                        
                        }
                }
            }
      post {
        always {
            archiveArtifacts artifacts: 'test_playbook.yaml', fingerprint: true 
        }
      }
}
