pipeline {
    agent any
    parameters {
        string(name: 'CredID', defaultValue: 'ST_OC_prom-gen1-as-CI00003333_upvk', description: 'Введите имя токена OpenShift')
    }
    stages {
        stage('Hello') {
            steps {
                script {
                    def reg = params.CredID =~ /^\w+_(\w+-\w+-?\w+)-(\w+)/
                }
            }
        }
        stage('Output') {
            input {
                message "Job will run with this params:\nOC foo\nbar foo\nCred = ${params.CredID}"
                ok "Yes, let's have a fun."
            }
            steps {
                println('Job with CredID: ${params.CredID} done.\nCluster: $reg[0][1]\nProject: $reg[0][2]')
            }
        }
    }
}
