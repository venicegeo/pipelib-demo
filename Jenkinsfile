#!/usr/bin/groovy

@Library('pipelib@shb/body') _

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
    mavenPull()
  }

  stage('Initial Scans') {
    dependencyCheck()
    ionConnect()
    sonar()
  }

  stage('CI Deploy') {
    cfPush()
    zap()
    cfBgDeploy()
  }

  stage('Integration Tests') {
    postman()
  }

  stage('Staging Deploy') {
    cfPush {
      cfTarget = 'stage'
    }
    cfBgDeploy {
      cfTarget = 'stage'
    }
  }

  stage('Final Scans') {
    fortify()
  }

  stage('Cleanup') {
    deleteDir()
  }
}
