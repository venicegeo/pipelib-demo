#!/usr/bin/groovy

@Library('pipelib@master') _

node {

  def u = new io.venicegeo.pipelib.Util(foobar: 'hello')

  stage('Parent Setup') {
    u.parent('https://github.com/venicegeo/pipelib-demo.git')
    u.setup()
  }

  stage('Setup') {
    git ([
      url: "https://github.com/venicegeo/pz-gateway.git",
      branch: 'master'
    ])
  }

//  stage('Integration Testing (int)') {
//    u.test_postman('int')
//  }

//  stage('Archive') {
//    u.nexus_post()
//  }

//  stage('CI Deploy (int)') {
//    u.cf_deploy('dev') // includes zap
//  }

//  stage('Scans') {
//    u.dependency_check()
//    u.ion_connect()
//    u.fortify()
//    u.sonar()
//  }

  stage('Cleanup') {
    deleteDir()
  }
}
