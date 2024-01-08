pipeline {
    agent any

    stages {
        stage('Upload to S3') {
            steps {
                script {
                    sh 'echo Working with S3'
                    sh 'aws configure set aws_access_key_id AKIAZTVI7FEFTZ6VBETE'
                    sh 'aws configure set aws_secret_access_key aJfdTqDHj3V/1uHZAk/fyM+VhM/hYhacRnyPaGEi'
                    sh 'aws s3 ls'
                    // Add your S3 upload commands here
                }
            }
        }
    }

    // Add more stages as needed
}
