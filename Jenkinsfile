#!/usr/bin/groovy

@Library('pipelib@v0.0.1')

def u = new io.venicegeo.pipelib.Util()

node {
  stage('Setup') {
    git ([
      url: "https://github.com/venicegeo/pipelib-demo.git",
      branch: 'master'
    ])
  }

  stage('Archive') {
    u.nexus_post()
  }

//  stage('CI Deploy (int)') {
//    u.cf_deploy('dev') // includes zap
//  }

  //stage('Scans') {
//    u.dependency_check()
//    u.ion_connect()
//    u.fortify()
   // u.sonar()
  //}
}
