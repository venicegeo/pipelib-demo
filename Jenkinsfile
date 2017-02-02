#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {
  stage('Archive') {
    nexusPost {
      host: "myhost.com"
    }
  }
}
