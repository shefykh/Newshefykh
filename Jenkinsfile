pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID = credentials('Account_id')
        AWS_DEFAULT_REGION="us-east-1"     
    }
        
    stages {
        stage('Infrastructure Deployment') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('aws_accesskey_id')
             AWS_SECRET_ACCESS_KEY = credentials('aws_secretaccesskey_id')
           }
           steps {
              script {
                  sh "terraform init"
                  sh "terraform validate"
                  sh "terraform plan"
                  sh "terraform ${action} --auto-approve"
            }
        }
               
     }
    }
    
}
