pipeline {
    agent any

    stages {
        stage('Upload to S3') {
            steps {
                script {
                    sh 'echo Working with S3'
                    sh 'aws configure set aws_access_key_id AKIAZTVI7FEFZ4F3DQJG'
                    sh 'aws configure set aws_secret_access_key 0svVqP2wSwUYM51W1K3wSjU2qRQYRGL4wn6tpUMG'
                    sh 'aws s3 ls'
                    // Add your S3 upload commands here
                }
            }
        }
    }

    // Add more stages as needed
}
