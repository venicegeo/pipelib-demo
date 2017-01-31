#!/usr/bin/groovy

@Library('pipelib@master')

def u = new io.venicegeo.pipelib.Util()

node {
  // first repository
  checkout([
    $class: 'GitSCM',
    branches: [[name: '*/master']],
    doGenerateSubmoduleConfigurations: false,
    extensions: [[$class: 'RelativeTargetDirectory',
                  relativeTargetDir: 'parentDirectory']],
    submoduleCfg: [],
    userRemoteConfigs: [[url: 'https://github.com/venicegeo/pipelib-demo.git']]
  ])

  checkout([
    $class: 'GitSCM',
    branches: [[name: '*/master']],
    doGenerateSubmoduleConfigurations: false,
    extensions: [[$class: 'RelativeTargetDirectory',
                  relativeTargetDir: 'childDirectory']],
    submoduleCfg: [],
    userRemoteConfigs: [[url: 'https://github.com/venicegeo/pz-gateway.git']]
  ])

  sh "ls -al"
  u.parentProperties = readProperties(file: 'parentDirectory/jenkins.properties')

  dir('childDirectory')
  sh "ls -al"

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
