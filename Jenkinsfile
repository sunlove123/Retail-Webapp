node {
    stage("Checkout"){
      git url: 'https://github.com/SudhirG85/Retail-Webapp.git'
    }
    stage("Build"){
      bat "mvn clean package"
      step([$class: 'ArtifactArchiver', artifacts: '**/target/*.war', fingerprint: true])
    }
    stage('Deploy') {
      echo 'Deploying..'
      bat 'echo %WORKSPACE%'
      bat 'set CATALINA_HOME=C:\\MyApplications\\apache-tomcat-8.5.9\nCALL C:\\MyApplications\\apache-tomcat-8.5.9\\bin\\shutdown.bat'
      bat 'COPY .\\target\\retailone.war C:\\MyApplications\\apache-tomcat-8.5.9\\webapps\\'
      bat 'set CATALINA_HOME=C:\\MyApplications\\apache-tomcat-8.5.9\nCALL C:\\MyApplications\\apache-tomcat-8.5.9\\bin\\startup.bat'
    }
    stage("Test"){
      bat "mvn integration-test"
      step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
      performanceReport compareBuildPrevious: false, configType: 'MRT', errorFailedThreshold: 0, errorUnstableResponseTimeThreshold: '', errorUnstableThreshold: 0, failBuildIfNoResultFile: false, modeOfThreshold: false, modePerformancePerTestCase: true, modeThroughput: false, nthBuildNumber: 0, parsers: [[$class: 'JMeterParser', glob: '**/TEST-*.xml']], relativeFailedThresholdNegative: 0.0, relativeFailedThresholdPositive: 0.0, relativeUnstableThresholdNegative: 0.0, relativeUnstableThresholdPositive: 0.0
    }
}
