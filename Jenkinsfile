pipeline {

    agent any

    stages {

        stage('Python Version') {
            steps {
                bat 'python --version'
            }
        }

        stage('Check Pip') {
            steps {
                bat '''
                python --version
                python -m pip --version
                where python
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '''
                dir
                type requirements.txt
                python -m pip install -r requirements.txt
                '''
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat 'python -m pytest'
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
