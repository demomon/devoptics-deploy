pipeline {
  agent any
  parameters {
    run description: '', filter: 'SUCCESSFUL', name: 'RUN', projectName: 'hex/demomon-devoptics/devoptics-build/master'
  }
  stages {
    stage('Build') {
      steps {
        devOpticsConsumes file: '', id: "devoptics-build-${RUN_NUMBER}", 
          jobName: "${RUN_JOBNAME}",
          masterUrl: '', runId: '${RUN}', type: 'demo'
      }
    }
  }
}
