@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage 'git'
  git url: "https://github.com/venicegeo/pipelib-demo.git", branch: 'master'

  sh 'git status'

  stage 'archive' {
    withEnv(["NEXUS_HOST=nexus.devops.geointservices.io",
             "NEXUS_ORG=venice",
             "NEXUS_REPO=Piazza",
             "NEXUS_TEAM=piazza",
             "APP=pipelibdemo",
             "EXT=txt"]) {
      u.to_nexus()
    }
  }
}
