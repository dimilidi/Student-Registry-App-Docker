 pipeline {
   agent any
   stages {  
      stage('NPM Install') {
            steps {
                bat 'npm install'
            }   
        }
      stage('Execute Tests') {
            steps {
                bat 'npm test'
            }   
        }
    }
}
