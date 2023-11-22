pipeline {
agent any

// environment {
//     AWS_ACCESS_KEY_ID     = credentials('AKIAZTVI7FEFXXESGEOH')
//     AWS_SECRET_ACCESS_KEY = credentials('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')
//     //SSH_KEY               = credentials('healthcare.pem')
// }

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
                    sh 'aws s3 ls'
                }
            }
        }
    }
}


