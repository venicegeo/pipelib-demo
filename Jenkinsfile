#!/usr/bin/groovy

@Library('pipelib@v0.1.0') _

def u = new io.venicegeo.pipelib.Util()

node {

  stage('Setup') {
    git ([
      url: "https://github.com/venicegeo/pz-gateway.git",
      branch: 'master'
    ])
  }

  stage('Archive') {
    u.nexus_post()
  }

  stage('CI Deploy (int)') {
    u.cf_deploy('dev') // includes zap
  }

  stage('Scans') {
    u.dependency_check()
    u.ion_connect()
    u.sonar()
    u.fortify()
  }

  stage('Cleanup') {
    deleteDir()
  }
}
