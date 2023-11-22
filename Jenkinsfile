pipeline {
agent any
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
                // withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'healthcare.pem', accessKeyVariable: 'AKIAZTVI7FEFXXESGEOH', secretKeyVariable: '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']]) {
                sh 'echo "Working with S3"'
                sh 'aws --version'
                sh 'aws s3 ls'
                sh 'pwd'
                }
            }
        }
    }
}


