@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage 'git'
  git url: "https://github.com/venicegeo/pipelib-demo.git", branch: 'master'

//  stage('archive') {
//    u.nexus_post()
//  }
  stage('fortify') {
    u.fortify()
  }

//  stage('CI Deploy (int)') {
//    u.cf_deploy('dev')
//  }


//  stage('scans') {
//    u.dependency_check()
//    u.ion_connect()
//  }
}
