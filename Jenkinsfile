// Filename: Jenkinsfile
node {
  def GITREPOREMOTE = "https://github.com/thuymo87/jenkins-databricks-demo.git"
  def GITBRANCH     = "main"

  stage('Checkout') {
    git branch: GITBRANCH, url: GITREPOREMOTE
  }  
}
