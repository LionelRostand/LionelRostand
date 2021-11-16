pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no root@192.168.1.38   mkdir /applis'
                 sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.38   export Home_applis=/applis'
                 sh 'ssh -oStrictHostKeyChecking=no root@192.168.1.38  chown youtechadmin:youtechadmin /applis'
            }


     }
   }
}
