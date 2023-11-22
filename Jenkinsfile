pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AKIAZTVI7FEFXXESGEOH')
        AWS_SECRET_ACCESS_KEY = credentials('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')
        SSH_KEY               = credentials('healthcare.pem')
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
                    sh ssh -i "${AAAAB3NzaC1yc2EAAAADAQABAAABAQDDMXwsfu7NF3OBMfUO/58XsUyRYBEy80lqqxWNsY5+jEd7dVoEp1oK9yVHM84wm2s2quMI1JTD0a+Z71N1wwWBFGeBik6j18jW7ZgF5FmobNizxs87Hd8gpcJRvOdMexMxm0GLKutjxQKIX3t80zAnIOVTWKHvAWMrUvYJk1aruDNeeS4c+2vP2w2czYJAQXvqWngfRBfn0bE/OK9k9srx1jo/17m65iKteZ9JQMld1mWt1BDPfiXwP1OMcxbQob9+P8hzlEIiUj7BWtRepoghc4uv2rl0o6yS7zvdaJGMgZbv90bEOj2bL9Y/HbX3/mDb9DuU70vOg+aWW/9TsTCV ubuntu@ip-172-31-14-205}" ubuntu@ec2-13-211-6-25.ap-southeast-2.compute.amazonaws.com 'aws s3 cp --recursive /home/abu/AWS_DevOps s3://mycloudines/demo-app/'
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


