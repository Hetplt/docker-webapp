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

        stage('Run Container') {
            steps {
                sh 'docker stop my-webapp || true'
                sh 'docker rm my-webapp || true'
                sh 'docker run -d --name my-webapp -p 8081:80 hetptl/my-webapp'
            }
        }
    }
}
