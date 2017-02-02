#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {
  stage('Archive') {
    mvnPut {
      app = 'pipelibdemo'
      packaging = 'txt'
    }
  }
}
