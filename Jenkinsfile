pipeline {
    agent any
    parameters {
        string(name: 'CredID', defaultValue: 'ST_OC_prom-gen1-as-CI00003333_upvk', description: 'Введите имя токена OpenShift')
    }
    stages {
        stage('Hello') {
            steps {
                script {
                    reg = params.CredID
                }
            }
        }
        stage('Output') {
            input {
                message "Job will run with this params:\nOC foo\nbar foo\nCred = ${params.CredID}"
                ok "Yes, let's have a fun."
            }
            steps {
                script{
                    println("Job with CredID: ${params.CredID} done.\nCluster: ${reg}")
                    //println params.reg[0]
                }
            }
        }
    }
}
