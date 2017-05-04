node {
    stage("Test"){
      git url: 'https://github.com/SudhirG85/Retail-Webapp.git'
      bat "mvn integration-test"
      step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
      performanceReport compareBuildPrevious: false, configType: 'MRT', errorFailedThreshold: 0, errorUnstableResponseTimeThreshold: '', errorUnstableThreshold: 0, failBuildIfNoResultFile: false, modeOfThreshold: false, modePerformancePerTestCase: true, modeThroughput: false, nthBuildNumber: 0, parsers: [], relativeFailedThresholdNegative: 0.0, relativeFailedThresholdPositive: 0.0, relativeUnstableThresholdNegative: 0.0, relativeUnstableThresholdPositive: 0.0
    }
}
