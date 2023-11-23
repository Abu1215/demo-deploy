pipeline {
agent any
stages {

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
