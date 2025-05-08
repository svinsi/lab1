pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'ec2-ssh-key', keyFileVariable: 'SSH_KEY')]) {
                    sh '''
                        chmod 600 $SSH_KEY
                        scp -i $SSH_KEY -o StrictHostKeyChecking=no index.html ec2-user@52.207.241.195:/tmp/index.html
                        ssh -i $SSH_KEY -o StrictHostKeyChecking=no ec2-user@52.207.241.195 'sudo mv /tmp/index.html /usr/share/nginx/html/index.html'
                    '''
                }
            }
        }
    }
}
