#!/usr/bin/groovy

@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  sh "ls -al"
  u.parentProperties = readProperties(file: 'jenkins.properties')

//  stage('Setup') {
//    git ([
//      url: "https://github.com/sbaxter/cli.git",
//      branch: 'master'
//    ])
//  }

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
