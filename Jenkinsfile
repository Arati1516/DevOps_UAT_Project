pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Python Version') {
            steps {
                bat '"C:\\Users\\USER1\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" --version'
            }
        }

        stage('Install Pytest') {
            steps {
                bat '"C:\\Users\\USER1\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" -m pip install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                bat '"C:\\Users\\USER1\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" -m pytest -v --junitxml=pytest-report.xml'
            }
        }
    }

    post {
        always {
            junit 'pytest-report.xml'
        }
    }
}