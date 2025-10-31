pipeline {
    agent any

    environment {
        PYTHON = 'C:\Users\91758\AppData\Local\Programs\Python\Python312\python.exe'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Python') {
            steps {
                bat "${env.PYTHON} --version"
            }
        }

        stage('Extract') {
            steps {
                bat "${env.PYTHON} etl.py"
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
