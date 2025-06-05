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
                sh 'scp index-aws.html ubuntu@3.87.54.65:/var/www/html/index.html'
            }
        }
        stage('Restart Nginx') {
            steps {
                sh 'ssh ubuntu@3.87.54.65 "sudo systemctl restart nginx"'
            }
        }
    }
}
