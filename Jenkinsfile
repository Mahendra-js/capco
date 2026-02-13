pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Mahendra-js/capco.git'
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
