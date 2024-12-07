pipeline{
    agent any
    environment{
        NODE_VERSION = 18.x
    }

    tools{
        nodejs "NODE_VERSION"
    }

    stages{

        stage('Checkout'){
            steps{
                git branch : 'main',  url: 'https://github.com/PKapralov/StudentRegistryAppDemo'

            }
        }
        stage("Install dependencies"){
            steps{
                script{
                    
                        bat
                         'npm install'
                    }
                }
            }
        }
        stage("Start application"){
            steps{
                script{
                    bat 'start /b npm start'
                    
                   
                }
            }
        }

        stage("run tests"){
            steps{
                 bat 'npm test'
            }
        }
    }

    post{
        always{
            echo "CI pipeline"
        }
    }
