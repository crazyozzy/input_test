pipeline {
    agent any
    parameters {
        string(name: 'CredID', defaultValue: 'ST_OC_prom-gen1-as-CI00003333_upvk', description: 'Введите имя токена OpenShift')
    }
    stages {
        stage('Hello') {
            steps {
                script {
                    def regex = params.CredID =~ /^\w+_(\w+-\w+-?\w+)-(\w+)/
                    reg1 = regex[0][1]
                    reg1 = regex[0][2]
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
                    println("Job with CredID: ${params.CredID} done.")
                    echo ("Cluster: " + reg1)
                    echo ("Project: " + reg2)
                    //println params.reg[0]
                }
            }
        }
    }
}
