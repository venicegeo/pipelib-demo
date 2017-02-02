#!/usr/bin/groovy

@Library('pipelib@shb/vars')

node {
  stage('Archive') {
    nexusPost {
      host: "myhost.com"
    }
  }
}
