pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/your-repo-url.git'
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG')]) {
                    sh 'kubectl apply -f deployment.yaml'
                }
            }
        }
    }
}
