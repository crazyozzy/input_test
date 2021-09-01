def foobar

pipeline {
    agent any
    
    stages {
        stage('Hello') {
            input {
                message "Should we continue?"
                ok "Yes, let's go."
                parameters {
                    credentials(name: 'sec_req', description: 'secret?')
                }
            }
            steps {
                println(sec_req)
            }
        }
    }
}
