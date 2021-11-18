pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               
                sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  mkdir /applis'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  cd /applis'
                 
                
            }
           }
         stage('Deploy') {
             steps {
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  touch test'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  chmod 775 test'
                
            }
           }
           stage('Destroy') {
             steps {
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  rm test'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  cd  .. && rmdir /applis'
                
            }
           }
   }
}
