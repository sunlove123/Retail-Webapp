pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                git 'https://github.com/SudhirG85/Retail-Webapp.git'
                bat 'mvn clean package'
            }
        }
    }
}
