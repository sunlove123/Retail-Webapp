pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                build '01Demo_Build'
            }
        }
        
        stage('Code Analysis')[
            steps {
                echo 'Running Code Analysis'
                build '02Demo_CodeAnalysis'
            }
        }
        stage('Testing') {
            steps {
                echo 'Testing..'
                build '03Demo_TestNG'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                build '04Demo_Deployment'
            }
        }
    }
}
