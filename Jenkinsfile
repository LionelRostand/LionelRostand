pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sshagent(credentials : ['use-the-id-from-credential-generated-by-jenkins']) {
                sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.37   uptime'
                }
                
            }


     }
   }
}
