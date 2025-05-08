pipeline {
    agent any

    stages {
        stage('Create page') {
            steps {
                writeFile file: 'index.html', text: '<h1>Hello from Jenkins!</h1>'
            }
        }

        stage('Deploy locally') {
            steps {
                sh '''
                    sudo cp index.html /usr/share/nginx/html/index.html
                '''
            }
        }
    }
}
