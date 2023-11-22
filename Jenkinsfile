pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AKIAZTVI7FEFXXESGEOH')
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

        stage('Deploy to EC2') {
            steps {
                script {
                    ssh -i "healthcare.pem" ubuntu@ec2-13-210-211-120.ap-southeast-2.compute.amazonaws.com
                }
            }
        }

        stage('Upload to S3') {
            steps {
                script {
                    withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'healthcare.pem', accessKeyVariable: 'AWS_ACCESS_KEY_ID', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                        sh 'aws s3 cp --recursive /home/abu/AWS_DevOps s3://mycloudines/demo-app/'
                    }
                }
            }
        }
    }
}


