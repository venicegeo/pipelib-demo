#!/usr/bin/groovy

@Library('pipelib@shb/vars') _

node {
  // Bring your own git repo.
  stage('Setup') {
    deleteDir()
    git([
      url: "https://github.com/venicegeo/pipelib-demo.git",
      branch: "master"
    ])
  }

  stage('Archive') {
    mavenPush()
  }

  stage('Initial Scans') {
    dependencyCheck()
    ionConnect()
    fortify()
  }

  stage('CI Deploy') {
    cfPush()
    zap()
    cfBgDeploy()
  }

  stage('Integration Tests') {
    postman()
  }

  stage('Final Scans') {
    fortify()
  }

  stage('Cleanup') {
    deleteDir()
  }
}
