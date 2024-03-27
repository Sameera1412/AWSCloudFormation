pipeline {
    agent any
    
    environment {
       AWS_ACCESS_KEY_ID     = credentials('ACCESS_KEY')
       AWS_SECRET_ACCESS_KEY = credentials('SECRET_KEY')
    }
    stages {
      stage('fetch_latest_code') {
        steps {
        git branch: 'main', url: 'https://github.com/Sameera1412/AWSCloudFormation/blob/main/ec2.yaml'
        }
      }
      stage('create stack'){
        steps{
            sh "aws cloudformation create-stack --stack-name CFJenkins –template-body file://ec2.yaml"
        }
      }
    }
 }
