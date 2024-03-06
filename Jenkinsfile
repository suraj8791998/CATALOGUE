pipeline{
    agent { node { label 'node' } }
    stages{
        stage{
            steps('INSTALL DEPENDENCIES'){
                sh 'npm install'
            }
        }
        stage{
            steps('UNIT TEST'){
                echo 'UNIT TEST IS SUCCESS'
            }
        }
        stage{
            steps('SONARQUBE'){
                sh 'sonar-scanner'
            }
        }
    }
}