@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage 'git'
  git url: "https://github.com/venicegeo/pipelib-demo.git", branch: 'master'

  sh 'git status'
  sh 'pwd'

  stage('archive') {
    u.nexus_push()
  }
}
