pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sshagent(['ec2-ssh-key']) {
                    sh """
                        scp index.html ec2-user@3.89.180.184:/tmp/index.html
                        ssh ec2-user@3.89.180.184 'sudo mv /tmp/index.html /usr/share/nginx/html/index.html'
                    """
                }
            }
        }
    }
}
