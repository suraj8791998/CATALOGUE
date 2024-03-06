pipeline{
    agent { node { label 'node' } }
    stages{
        stage('INSTALL DEPENDENCIES'){
            steps{
                sh 'npm install'
            }
        }
        stage('UNIT TEST'){
            steps{
                echo 'UNIT TEST IS SUCCESS'
            }
        }
        stage('SONARQUBE'){
            steps{
                sh 'sonar-scanner'
            }
        }
    }
}