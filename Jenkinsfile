node {
  def myGradleContainer = docker.image('gradle:jdk8')
  myGradleContainer.pull()
  stage('prep') {
    checkout scm
  }
  stage('test') {
     myGradleContainer.inside("-v "C:\Users\squ926\jenkins_home\.gradle":/home/gradle/.gradle") {
       sh 'cd complete && gradle test'
     }
  }
  stage('run') {
     myGradleContainer.inside("-v "C:\Users\squ926\jenkins_home\.gradle":/home/gradle/.gradle") {
       sh 'cd complete && gradle run'
     }
  }
}
