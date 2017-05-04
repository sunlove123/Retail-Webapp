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
                bat 'echo %WORKSPACE%'
                bat 'set CATALINA_HOME=C:\\MyApplications\\apache-tomcat-8.5.9\nCALL C:\\MyApplications\\apache-tomcat-8.5.9\\bin\\shutdown.bat'
                bat 'COPY .\\target\\retailone.war C:\\MyApplications\\apache-tomcat-8.5.9\\webapps\\'
                bat 'set CATALINA_HOME=C:\\MyApplications\\apache-tomcat-8.5.9\nCALL C:\\MyApplications\\apache-tomcat-8.5.9\\bin\\startup.bat'
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
