pipeline {
  agent {
     node {
       label 'docker-vm'
     }
   }
     parameters {
       int(name: 'Image_Tag', description: "Please insert image tag you won't upload to ECR")
       }
    stages {
        stage('Pull and Push image to ECR') {
            steps {
                sh 'ansible-playbook -i hosts pull_and_push.yml'
            }
        }
        stage('deploy the app from module 6') {
            steps {
                sh 'kubectl create -f deploy_app.yml'
            }
        }
    }
}