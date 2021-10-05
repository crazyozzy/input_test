pipeline {
    agent any
    
    stages {
        stage('Hello') {
            steps {
                input {
                    message "Please, choose cred from apropriate project"
                    ok "Yes, let's have a fun."
                    parameters {
                        credentials(name: 'sec_req', description: 'select cred')
                    }
                }
                println("Credential ID: ${sec_req}")
            }
        }
    }
}
