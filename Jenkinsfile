properties([parameters([choice(choices: ['us-east-1', 'us-east-2', 'us-west-1'], description: 'regions to be enabled', name: 'region')])])
pipeline{
    agent any 
    stages{
        stage('chkout'){
            steps{
               
            }
        }
        stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
         stage('terraform validate'){
            steps{
                sh 'terraform validate'
            }
        }
        stage('terraform plan'){
            steps{
                sh 'terraform plan'
            }
        }
        stage('second-parajob'){
            steps{
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
