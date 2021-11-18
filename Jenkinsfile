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
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  touch /applis/test'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  chmod 775 /applis/test'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91 ls -lrt /applis/test '
                
            }
           }
           stage('Destroy') {
             steps {
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  rm /applis/test'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  rmdir /applis'
                
            }
           }
         stage('install') {
             steps {
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91 apt update'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  apt install docker.io -y  && apt install ansible -y'
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  systemctl enable docker '
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  systemctl status docker '
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91  systemctl start docker '
            }
           }
          stage('install') {
             steps {
                 sh 'ssh -o StrictHostKeyChecking=no  root@192.168.1.91 docker ps -a'
                 
            }
           }
   }
}
