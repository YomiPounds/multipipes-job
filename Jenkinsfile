properties([parameters([choice(choices: ['us-east-1', 'us-east-2', 'us-west-1'], description: 'regions to be enabled', name: 'region')])])
pipeline{
    agent any 
    stages{
        stage('chkout'){
            steps{
               checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkinsgit', url: 'https://github.com/YomiPounds/multipipes-job.git']]])
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
