pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173   uptime'
            }

        }
        stage('Test') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173 apt update'
                 sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173 ls -lrt'
            }

        }


    }
}
