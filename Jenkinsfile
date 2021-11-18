pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no root@192.168.1.91   mkdir /applis'
                 sh 'ssh -oStrictHostKeyChecking=no root@192.168.1.91   export Home_applis=/applis'
                 sh 'ssh -oStrictHostKeyChecking=no root@192.168.1.91  chown youtechadmin:youtechadmin /applis'
            }

        }
        stage('Test') {
            steps {
                 sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  echo $Home_applis'
                
                sh '''
                   ssh -oStrictHostKeyChecking=no  root@192.168.1.91  touch /applis/toto.txt  
                '''
                 sh '''
                   ssh -oStrictHostKeyChecking=no  root@192.168.1.91  ls -lrt  /applis/toto.txt  
                '''
            
                 
            }

        }
       stage('deploy') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  chmod 755 /applis/toto.txt'
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  ls -lrt /applis/toto.txt'
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  cat /applis/toto.txt'
               
            }

        }
       stage('destroy') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91 rm -rf /applis/*'
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  rmdir /applis'
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91 who'
                
            }

        }
        
         stage('docker') {
            steps {
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91 service docker status '
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  docker ps -a'
                 sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  docker run -p 8081 --name ngin -d nginx'
                sh 'ssh -oStrictHostKeyChecking=no  root@192.168.1.91  docker ps -a'
            }

        }


    }
}
