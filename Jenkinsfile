pipeline {
    agent any
    parameters {
        string(name: 'CredlID', defaultValue: '', description: 'Введите имя токена OpenShift')
    }
    stages {
        stage('Hello') {
            input {
                message "Job will run with this params:\nOC\n${CredentialID}"
                ok "Yes, let's have a fun."
            }
            steps {
                println("Job with CredID ${CredID} done.")
            }
        }
    }
}
