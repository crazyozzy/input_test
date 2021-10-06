import jenkins.*
import jenkins.model.* 
import hudson.*
import hudson.model.*
def jenkinsCredentials = com.cloudbees.plugins.credentials.CredentialsProvider.lookupCredentials(
        com.cloudbees.plugins.credentials.Credentials.class,
        Jenkins.instance,
        null,
        null
);
for (creds in jenkinsCredentials) {
    println(jenkinsCredentials.id)
    }

pipeline {
    agent any
    parameters {
        credentials(name: 'sec_req', description: 'select cred')
    }
    stages {
        stage('Hello') {
            input {
                message "Should we continue?"
                ok "Yes, let's have a fun."
                parameters {
                    credentials(name: 'sec_req_input', description: 'select cred')
                }
            }
            steps {
                println("Credential ID: ${sec_req}")
                println("Credential ID: ${sec_req_input}")
                println("${folder}")
            }
        }
    }
}
