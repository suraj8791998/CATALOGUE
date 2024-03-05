pipeline{
    agent { node { label 'node' } }
    stages{
        stage('INSTALL DEPENDENCIES'){
            steps{
                sh 'npm install'
            }
        }

        stage('Unit test') {
            steps {
                echo "unit testing is done here"
            }
        }

        stage('sonnar-scanner'){
            steps{
                sh 'sonar-scanner'
            }
        }

        stage('Deploy'){
            steps{
                echo "Deploy"
            }
        }
    }
}