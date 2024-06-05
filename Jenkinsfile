pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="339712885650"
        AWS_DEFAULT_REGION="us-east-1"     
    }
        
    stages {
        stage('KHADIJAT Infrastructure Deployment') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('Access key')
             AWS_SECRET_ACCESS_KEY = credentials('Secret_Key')
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
