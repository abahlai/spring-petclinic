node("ops-slave") {
   def mvnHome
   def GIT_REPO_URL
   def GIT_BRANCH

 stage ('Initialize')
 {
    // Get the Maven tool.
       mvnHome = tool 'Maven 3'
    // Git repo
        GIT_REPO_URL = "git@github.com:MykolaKr/spring-petclinic.git"
        GIT_BRANCH   = "${sha1}"
 }

 stage('Checkout') { // for display purposes
     git url: "${GIT_REPO_URL}" , branch: "${GIT_BRANCH}"
 }

 stage('Build') {
      sh "${mvnHome}/bin/mvn clean build"
 }

 stage('Archive') {
     archive 'target/*.jar'
 }
}