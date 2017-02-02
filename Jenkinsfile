#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {
  stage('Archive') {
    nexusPost {
      NEXUS_HOST = "myhost.com"
    }
  }
}
