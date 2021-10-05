pipeline {
    agent any
    parameters {
        credentials(name: 'sec_req', description: 'select cred')
    }
    stages {
        stage('Hello') {
            steps {
                println("Credential ID: ${sec_req}")
            }
        }
    }
}
