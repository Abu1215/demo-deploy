pipeline {
    agent any

    environment {
        AWS_REGION = 'ap-southeast-2'
        S3_BUCKET_NAME = 'mycloudines'
        EC2_INSTANCE_IP = '3.25.246.146'
        KEY_PAIR_NAME = 'healthcare.pem'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from GitHub
                git 'https://github.com/Abu1215/demo-deploy.git'
            }
        }

        // stage('Build') {
        //     steps {
        //         // Assuming your website is a Node.js app, install dependencies and build
        //         sh 'npm install'
        //         sh 'npm run build'
        //     }
        // }

        stage('Upload to S3') {
            steps {
                // Use the AWS CLI to upload the built artifacts to S3
                script {
                    withAWS(region: env.AWS_REGION, credentials: 'AKIAZTVI7FEFXXESGEOH') {
                        sh "aws s3 sync dist/ s3://${env.S3_BUCKET_NAME}/"
                    }
                }
            }
        }

        stage('Deploy to EC2') {
            steps {
                // Copy artifacts to EC2 instance using SSH
                script {
                    sshagent(['ssh -i "healthcare.pem" ubuntu@ec2-3-25-246-146.ap-southeast-2.compute.amazonaws.com']) {
                        sh "scp -r -i /var/lib/jenkins/.ssh/${env.KEY_PAIR_NAME}.pem dist/* ec2-user@${env.EC2_INSTANCE_IP}:/path/to/your/webserver/root"
                    }
                }
            }
        }
    }

    post {
        success {
            // Notify on success
            echo 'Build, upload, and deployment successful!'
        }
        failure {
            // Notify on failure
            echo 'Build, upload, or deployment failed. Please check the logs for more information.'
        }
    }
}
