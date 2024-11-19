pipeline {
    agent { label 'vamobora' }
    tools {
        terraform 'terraform'
    }
    stages {
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
                }
        }
        stage('Terraform destroy') {
            steps {
                input 'Você quer destruir o cluster?'
                sh 'terraform destroy -auto-approve'
                }    
            }
        }
    }
