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
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                bat 'set CATALINA_HOME=C:\\MyApplications\\apache-tomcat-8.5.9\necho %WORKSPACE%\nC:\\MyApplications\\apache-tomcat-8.5.9\\bin\\shutdown.bat\nCOPY .\\target\\retailone.war C:\\MyApplications\\apache-tomcat-8.5.9\\webapps\\nC:\\MyApplications\\apache-tomcat-8.5.9\\bin\\startup.bat'
            }
        }  
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'mvn integration-test'
            }
        }          
    }
}
