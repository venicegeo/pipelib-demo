#!/usr/bin/groovy

@Library('pipelib@master')

def parentProperties = new Properties()
def propertiesFile = new File('jenkins.properties')
propertiesFile.withInputStream {
  parentProperties.load(it)
}

def u = new io.venicegeo.pipelib.Util(parentProperties: parentProperties)

node {

  stage('Setup') {
    git ([
      url: "https://github.com/open-sensor-hub/osh-js.git",
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

//  stage('Cleanup') {
//    deleteDir()
//  }
}
