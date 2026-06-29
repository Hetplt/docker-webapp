pipeline {

    agent any

    stages {

        stage('Docker Build') {
            steps {
                sh 'docker build -t hetptl/my-webapp .'
            }
        }


        stage('Docker Push') {
            steps {
                sh 'docker push hetptl/my-webapp'
            }
        }


        stage('Kubernetes Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }


        stage('Verify Deployment') {
            steps {
                sh 'kubectl get pods'
                sh 'kubectl get svc'
            }
        }
    }
}
