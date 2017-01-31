#!/usr/bin/groovy

@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  stage('Parent Setup') {
    u.parent('https://github.com/venicegeo/pipelib-demo.git')
  }

  stage('Setup') {
    git ([
      url: "https://github.com/venicegeo/pz-gateway.git",
      branch: 'master'
    ])
  }

  stage('Test') {
    u.proptest()
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
