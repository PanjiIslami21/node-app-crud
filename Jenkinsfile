pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t node-crud .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker stop node-crud || true'
                sh 'docker rm node-crud || true'
                sh 'docker run -d -p 3000:3000 --name node-crud node-crud'
            }
        }
    }
}