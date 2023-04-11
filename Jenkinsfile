// Jenkinsfile
node {
  //def GITREPO         = "/var/lib/jenkins/workspace/${env.JOB_NAME}"
  def GITREPO         = "/c/ProgramData/Jenkins/.jenkins/workspace/${env.JOB_NAME}"
  def GITREPOREMOTE   = "https://github.com/chiragsaroliya/jenkinsLearning.git"
  def GITHUBCREDID    = "git-adb-demo-project"
  def CURRENTRELEASE  = "main"
  def DBTOKEN         = "adb-pat-token"
  def DBURL           = "https://adb-8754731172690151.11.azuredatabricks.net/"
  def ADBTOKEN = "dapi96a5342f7f6a74d0c5810f262ea55c78-2"
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
  
  stage('Setup') {
    sh """#!/bin/bash
        # Configure Conda environment for deployment & testing
        # source ${CONDAPATH}/Scripts/activate ${CONDAENV}
        echo "======================inside setup stage ============================"
      """
  }
}
