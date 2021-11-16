pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'ssh  root@192.168.1.38   mkdir /applis'
                 sh 'ssh  root@192.168.1.38   export Home_applis=/applis'
                 sh 'ssh  root@192.168.1.38  chown youtechadmin:youtechadmin /applis'
            }


     }
   }
}
