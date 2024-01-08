pipeline {
    agent any

    stages {
        stage('Upload to S3') {
            steps {
                script {
                    sh 'echo Working with S3'
                    sh 'aws configure set aws_access_key_id AKIAZTVI7FEFR2ZF75QT'
                    sh 'aws configure set aws_secret_access_key lzpLe3Si4s4/jO80at9p60+1W1xGK0BR8JI6/3QC'
                    sh 'aws s3 ls'
                    // Add your S3 upload commands here
                }
            }
        }
    }

    // Add more stages as needed
}
