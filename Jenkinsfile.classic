pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        step([$class: 'CopyArtifact', projectName: 'hat/demomon/devoptics-build/master'])
        archiveArtifacts artifacts: '*.sh', fingerprint: true
      }
    }
  }
}
