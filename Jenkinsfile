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
                sh 'zip -r ./* Jenkinsfile.zip --exclude=.git --exclude=.zip'
                sh 'ls -ltr'
            }
        }
        stage('PUBLISH ARTIFACTOR'){
            steps{
                nexusArtifactUploader(
                nexusVersion: 'nexus3',
                protocol: 'http',
                nexusUrl: '44.213.147.229:8081',
                groupId: 'com.cart',
                version: '1.0.0',
                repository: 'catalogue',
                credentialsId: 'nexus-auth',
                artifacts: [
                    [artifactId: 'catalogue',
                        classifier: '',
                        file: 'Jenkinsfile.zip',
                        type: 'jar']
                ]
                )
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