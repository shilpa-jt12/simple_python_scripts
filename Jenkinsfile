pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Python Version') {
            steps {
                bat 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat 'pytest'
            }
        }

    }

    post {

        success {
            echo 'Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }

        always {
            echo 'Pipeline execution finished.'
        }

    }

}
