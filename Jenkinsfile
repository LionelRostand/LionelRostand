pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173   mkdir /applis'
                 sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173   export Home_applis=/applis'
                 sh 'ssh -oStrictHostKeyChecking=no root@62.171.191.173  chown youtechadmin:youtechadmin /applis'
            }

        }
        stage('Test') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  touch /applis/toto.txt'
            
                 
            }

        }
       stage('deploy') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  chmod 755 /applis/toto.txt'
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  ls -lrt /applis/toto.txt'
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  cat /applis/toto.txt'
            }

        }
       stage('destroy') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173 rm -rf /applis/*'
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  rmdir /applis'
                
            }

        }


    }
}
