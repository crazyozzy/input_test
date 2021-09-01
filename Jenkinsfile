pipeline {
    agent any
    
    stages {
        stage('Hello') {
            input {
                message "Should we continue?"
                ok "Yes, let's have a fun."
                parameters {
                    credentials(name: 'sec_req', description: 'secret?')
                }
            }
            steps {
                println("Credential ID: ${sec_req}")
            }
        }
    }
}
