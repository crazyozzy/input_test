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
                    credentials(name: 'sec_req', description: 'select cred')
                }
            }
            steps {
                println("Credential ID: ${sec_req}")
            }
        }
    }
}
