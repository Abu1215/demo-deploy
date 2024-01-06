pipeline {
    agent any

    environment {
        AWS_CREDENTIALS = credentials('AIDAZTVI7FEFWLQU22X6P')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    git 'https://github.com/Abu1215/demo-deploy.git'
                }
            }
        }

        stage('Upload to S3') {
            steps {
                script {
                    sh 'echo "Working with S3"'
                    sh 'aws --version'
                    sh "aws configure set aws_access_key_id AKIAZTVI7FEF2Y7TWOXF"
                    sh "aws configure set aws_secret_access_key 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"
                    sh 'aws s3 ls'
                    sh 'pwd'
                    sh 'aws s3 cp . s3://mycloudines/ --recursive --acl public-read'
                }
            }
        }
    }
}
