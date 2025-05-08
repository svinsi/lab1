pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sshagent(['ec2-ssh-key']) {
                    sh """
                        scp index.html ec2-user@52.207.241.195:/tmp/index.html
                        ssh ec2-user@52.207.241.195 'sudo mv /tmp/index.html /usr/share/nginx/html/index.html'
                    """
                }
            }
        }
    }
}
