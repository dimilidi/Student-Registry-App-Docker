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
    }
}
