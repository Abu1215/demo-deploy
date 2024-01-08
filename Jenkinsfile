pipeline {
    agent any

    stages {
        // Uncomment the stage you need, and add more stages if necessary
    
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
                 //   sh 'aws s3 cp . s3://mycloudines/ --recursive --acl public-read'
                }
            }
        }
    }

    // Additional pipeline configuration (post, environment, etc.) can go here
}
