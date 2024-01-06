pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AKIAZTVI7FEF2Y7TWOXF')
        AWS_SECRET_ACCESS_KEY = credentials('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')
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
                    sh 'aws s3 ls'
                    sh 'pwd'
                    sh 'aws s3 cp . s3://mycloudines/ --recursive --acl public-read'
                }
            }
        }
    }
}

