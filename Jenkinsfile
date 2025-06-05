pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/deepshikha-dubey/nginx-deployment.git'
            }
        }
        stage('Deploy to AWS') {
            steps {
                sh 'scp index-aws.html ubuntu@52.91.210.191:/var/www/html/index.html'
            }
        }
        stage('Restart Nginx') {
            steps {
                sh 'ssh ubuntu@52.91.210.191 "sudo systemctl restart nginx"'
            }
        }
    }
}
