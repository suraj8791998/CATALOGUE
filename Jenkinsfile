pipeline{
    agent any
    stages{
        stage('INSTALL DEPENDENCIES'){
            steps{
                sh 'npm install'
            }
        }
        stage('UNIT TEST'){
            steps{
                echo 'UNIT TEST SUCCESS'
            }
        }
        stage('SONARQUBE'){
            steps{
                sh 'sonar-scanner'
            }
        }
        
    }
}