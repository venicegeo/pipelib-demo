@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage('Archive') {
    withEnv(["NEXUS_HOST=nexus.devops.geointservices.io",
             "NEXUS_ORG=venice",
             "NEXUS_REPO=Piazza",
             "NEXUS_TEAM=piazza",
             "APP=pipelibdemo",
             "EXT=txt"]) {
      git url: "https://github.com/venicegeo/pipelib-demo.git"
      u.to_nexus()
    }
  }
}
