pipeline {
    agent any
   

    tools {
        nodejs "Node_18" // Това трябва да съвпада с инсталираната версия в Jenkins
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/PKapralov/StudentRegistryAppDemo'
            }
        }

        stage("Install dependencies") {
            steps {
                script {
                    bat 'npm install'
                }
            }
        }

        stage("Start application") {
            steps {
                script {
                    bat 'start /b npm start'
                }
            }
        }

        stage("Run tests") {
            steps {
                bat 'npm test'
            }
        }
    }

    post {
        always {
            echo "CI pipeline"
        }
    }
}
