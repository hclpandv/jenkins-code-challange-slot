pipeline {
    agent {
        node { label 'web-server' }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'echo yum install httpd -y'
                sh 'echo yum install rpm-build -y'
                sh 'echo yum install epel-release -y'
                sh 'echo yum install npm -y'
                sh 'echo $(hostname -s)'
                sh 'echo npm run build:rpm' 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo rpm -ip netent-slot-1.0.1-1.el7.centos.x86_64.rpm' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
            }
        }
    }
}
