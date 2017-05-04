node {
    stage("Checkout"){
      git url: 'https://github.com/SudhirG85/Retail-Webapp.git'
    }
    stage("Build"){
      bat "mvn clean install"
      step([$class: 'ArtifactArchiver', artifacts: '**/target/*.war', fingerprint: true])
      def server = Artifactory.server 'ArtifactoryLocal'
      def uploadSpec = """{
        "files": [
        {
            "pattern": "target/*.war",
            "target": "DemoRepo/com/cts/sample/retainone/0.0.1-SNAPSHOT/"
        }
        ]
      }"""
      server.upload(uploadSpec)
    }
}
