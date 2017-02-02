#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {

  stage('Setup') {
    git ([
      url: "https://github.com/venicegeo/pz-gateway.git",
      branch: 'master'
    ])
  }

  stage('Archive') {
    nexusPost {
      host: "myhost.com"
    }
  }

  stage('Cleanup') {
    deleteDir()
  }
}
