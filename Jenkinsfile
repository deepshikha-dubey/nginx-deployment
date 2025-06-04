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
                sh 'scp index-aws.html ubuntu@AWS-IP:/var/www/html/index.html'
            }
        }
        stage('Restart Nginx') {
            steps {
                sh 'ssh ubuntu@AWS-IP "sudo systemctl restart nginx"'
            }
        }
    }
}
