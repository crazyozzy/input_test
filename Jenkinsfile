pipeline {
    agent any
    parameters {
        input {
            message "Please, choose cred from apropriate project"
            ok "Yes, let's have a fun."
            parameters {
                credentials(name: 'sec_req', description: 'select cred')
            }
        }          
    }
    stages {
        stage('Hello') {
            steps {
                println("Credential ID: ${sec_req}")
            }
        }
    }
}
