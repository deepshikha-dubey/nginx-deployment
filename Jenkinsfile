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
                sh 'scp index-aws.html ubuntu@100.26.194.100:/var/www/html/index.html'
            }
        }
        stage('Restart Nginx') {
            steps {
                sh 'ssh ubuntu@100.26.194.100 "sudo systemctl restart nginx"'
            }
        }
    }
}
