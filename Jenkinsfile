@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage 'git'
  git url: "https://github.com/venicegeo/pipelib-demo.git", branch: 'master'

  stage('archive') {
    u.nexus_post()
  }

  stage('fetch') {
    u.nexus_get()
  }

  stage('scans') {
    u.ion_connect()
  }
}
