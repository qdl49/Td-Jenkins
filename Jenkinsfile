properties([
  pipelineTriggers([pollSCM('H/3 * * * *')])
  ])
node() {
  cleanWs()
  checkout scm
  sh "make"
  sh "./main"
}
node {
  stage('build1') {
    sh 'make'
  }
  stage('checkout1') {
    checkout scm
  }
  stage('archivage1') {
    archiveArtifacts artifacts: 'main', onlyIfSuccessful: true
  }
}
