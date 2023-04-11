// Jenkinsfile
node {
  //def GITREPO         = "/var/lib/jenkins/workspace/${env.JOB_NAME}"
  def GITREPO         = "/c/ProgramData/Jenkins/.jenkins/workspace/${env.JOB_NAME}"
  def GITREPOREMOTE   = "https://github.com/chiragsaroliya/jenkinsLearning.git"
  def GITHUBCREDID    = "git-adb-demo-project"
  def CURRENTRELEASE  = "main"
  def DBTOKEN         = "adb-pat-token"
  def DBURL_DEV           = "https://adb-8754731172690151.11.azuredatabricks.net/"
  def ADBTOKEN_DEV = "dapi96a5342f7f6a74d0c5810f262ea55c78-dev"
  def DBURL_STAGE           = "https://adb-8754731172690152.12.azuredatabricks.net/"
  def ADBTOKEN_STAGE = "dapi96a5342f7f6a74d0c5810f262ea55c78-stage"
  def SCRIPTPATH      = "${GITREPO}/scripts"
  def NOTEBOOKPATH    = "${GITREPO}/notebook"
  //def DBFSPATH        = "dbfs:<dbfs-path>"
  def CLUSTERID       = "0815-091341-sm7iisdg"
  def ORGID=8754731172690151

  stage('Checkout') { // for display purposes
    echo "Pulling ${CURRENTRELEASE} Branch from Github"
    git branch: CURRENTRELEASE, credentialsId: GITHUBCREDID, url: GITREPOREMOTE
    sh "pwd"
    echo " **************************** Checkout complete ***********************"
    sh "ls"
  }
  
  stage('dev') {
    def myObject = [url: "${DBURL_DEV}", token: "${ADBTOKEN_DEV}", env: 'DEV']
    echo "$myObject"
    myFunction(myObject)
    sh """#!/bin/bash
        echo "======================inside setup stage ============================"
      """
  }
}

def myFunction(adbconfig) {
  for (item in adbconfig) {
    echo " ===== ${item.url} ====="
  }
}
