node {
    stage("Checkout"){
      git url: 'https://github.com/SudhirG85/Retail-Webapp.git'
      bat "C:\\MyApplications\\Sonar\\sonar-scanner-2.8\\bin\\sonar-runner -Dsonar.host.url=http://localhost:9000  -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectName=Retail-Webapp1 -Dsonar.projectVersion=1.0 -Dsonar.projectKey=Retail-Webapp1 -Dsonar.sources=src"
    }
}
