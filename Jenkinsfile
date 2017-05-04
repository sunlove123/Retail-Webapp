node('master') {
  git url: 'https://github.com/SudhirG85/Retail-Webapp.git'
  def v = version()
  if (v) {
    echo "Building version ${v}"
  }
  bat "mvn integration-test"
  step([$class: 'ArtifactArchiver', artifacts: '**/target/*.war', fingerprint: true])
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}
def version() {
  def matcher = readFile('pom.xml') =~ '<version>(.+)</version>'
  matcher ? matcher[0][1] : null
}
