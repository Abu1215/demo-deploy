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

s
        stage('Upload to S3') {
            steps {
                script {
                    {
                        sh 'aws s3 cp --recursive /home/abu/AWS_DevOps s3://mycloudines/demo-app/'
                    }
                }
            }
        }
    }
}


