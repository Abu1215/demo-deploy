pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID = credentials('AKIAZTVI7FEFXXESGEOH')
        AWS_SECRET_ACCESS_KEY = credentials('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')
        GITHUB_USERNAME = credentials('Abu1215')
        GITHUB_TOKEN = credentials('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')
    }

    stages {
        stage('Prepare') {
            steps {
                git branch: 'master',
                    credentialsId: 'Abu1215',
                    url: 'https://github.com/Abu1215/demo-deploy.git'
            }
        }


        stage('Deploy to AWS S3') {
            steps {
                sh 'aws s3 cp . s3://mycloudines/demo-app/'
            }
        }

        stage('Deploy to EC2') {
            steps {
                sshagent(['healthcare.pem']) {
                    sh 'scp -r -i healthcare.pem . ubuntu@ec2-13-211-6-25.ap-southeast-2.compute.amazonaws.com:/home/abu/AWS_DevOps/'
                }
            }
        }
    }
}