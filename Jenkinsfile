pipeline {
    agent any
    stages {  
        stage('NPM Install') {
            steps {
                bat 'npm install'
            }   
        }
        stage('Tests') {
            parallel {
                stage('Run npm audit tests') {
                    steps {
                        bat 'npm audit'
                    }   
                }
                stage('Execute Tests') {
                    steps {
                        bat 'npm test'
                    }   
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging'
            }   
        }
        stage('Approval for Production Deployment') {
            steps {
                script {
                    input message: 'Approve deployment to Production?', ok: 'Deploy'
                }
            }   
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production'
            }   
        }
    }
}
