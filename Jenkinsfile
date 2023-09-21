import hudson.EnvVars;
import hudson.slaves.EnvironmentVariablesNodeProperty;
import hudson.slaves.NodeProperty;
import hudson.slaves.NodePropertyDescriptor;
import hudson.util.DescribableList;
import jenkins.model.Jenkins;
public createGlobalEnvironmentVariables(String key, String value){

       Jenkins instance = Jenkins.getInstance();
 
       DescribableList<NodeProperty<?>, NodePropertyDescriptor> globalNodeProperties = instance.getGlobalNodeProperties();
       List<EnvironmentVariablesNodeProperty> envVarsNodePropertyList = globalNodeProperties.getAll(EnvironmentVariablesNodeProperty.class);
 
       EnvironmentVariablesNodeProperty newEnvVarsNodeProperty = null;
       EnvVars envVars = null;
 
       if ( envVarsNodePropertyList == null || envVarsNodePropertyList.size() == 0 ) {
           newEnvVarsNodeProperty = new hudson.slaves.EnvironmentVariablesNodeProperty();
           globalNodeProperties.add(newEnvVarsNodeProperty);
           envVars = newEnvVarsNodeProperty.getEnvVars();           
       } else {
           //We do have a envVars List           
           envVars = envVarsNodePropertyList.get(0).getEnvVars();
       }
       envVars.put(key, value)

       instance.save()
}
pipeline {@Library('globalvarhelper')
    agent any 
        #parameters {
         #   string(defaultValue: "123", description: 'This is an activityID', name: 'activityID')
          #  }
    environment {         ACTIVITY_ID = '1234!'     }
            stages {
                stage('Example') {             steps {  
                    createGlobalEnvironmentVariables("activityID", "121212154")
                                             }
                         }
        
               stage('Trigger Second Jenkinsfile') {
                    steps {
                        build job: "../javawebproject/master", wait: true, parameters: [string(name: 'activityID', value: "${ACTIVITY_ID}")]
                        }
                }
            }
  
}

