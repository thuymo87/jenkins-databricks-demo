// Filename: Jenkinsfile
node {
  def GITREPOREMOTE = "https://github.com/thuymo87/jenkins-databricks-demo.git"
  //def GITBRANCH     = "main"
  def GITBRANCH = "develop"
  def DBCLIPATH     = "/usr/local/bin"
  def JQPATH        = "/usr/local/bin"
  def JOBPREFIX     = "jenkins-demo"
  //def BUNDLETARGET  = "dev"
  def BUNDLETARGET = "qa"

  stage('Checkout') {
    git branch: GITBRANCH, url: GITREPOREMOTE
  }
  stage('Validate Bundle') {
    sh """#!/bin/bash
          ${DBCLIPATH}/databricks bundle validate -t ${BUNDLETARGET}
       """
  }
  stage('Deploy Bundle') {
    sh """#!/bin/bash
          ${DBCLIPATH}/databricks bundle deploy -t ${BUNDLETARGET}
       """
  }
  // stage('Run Notebook') {
  //   sh """#!/bin/bash
  //         ${DBCLIPATH}/databricks bundle run -t ${BUNDLETARGET} hello-job
  //      """
  // }
  stage('Run pipeline') {
    sh """#!/bin/bash
          ${DBCLIPATH}/databricks bundle run -t ${BUNDLETARGET} databricks_jenkins_demo_job 
       """
  }
}