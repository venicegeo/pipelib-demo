#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {
  // Bring your own git repo.
  stage('Setup') {
    git([
      url: "https://github.com/venicegeo/pipelib-demo.git",
      branch: "master"
    ])
  }

  stage('Archive') {
    mvnPut {
      app = 'pipelibdemo'
      packaging = 'txt'
    }
  }
}
