pipeline {
    agent any

    stages {
        stage('Pull from Git') {
            steps {
                git branch: 'main',
                    credentialsId: 'Docker_Learning_with_jenkins',
                    url: 'https://github.com/gyvijay/CICD_test.git'
            }
        }

        stage('Build Docker') {
            steps {
                bat 'docker build -t cicd_test_pipeline .'
            }
        }
        
        stage('print Docker Images') {
            steps {
                bat 'docker images'
            }
        }

        stage('Run Docker') {
            steps {
                bat 'docker run --rm --name cicd_test_container cicd_test_pipeline'
            }
        }
    }
}
