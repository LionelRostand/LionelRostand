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
                 sh "ssh -oStrictHostKeyChecking=no root@62.171.191.173  echo 'bonjour  a vous' > /applis/toto.txt"
                 
            }

        }
       stage('deploy') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@62.171.191.173  cat touch /applis/toto.txt'

            }

        }


    }
}
