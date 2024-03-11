pipeline{
    agent { node { label 'my_agent' } }
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
        stage('BUILD'){
            steps{
                sh 'zip -r ./* catalogue.zip --exclude=.git --exclude=.zip'
            }
        }
        
    }
    post{
        always{
            //cleaning workspace directory
            deleteDir()
        }
    }
}