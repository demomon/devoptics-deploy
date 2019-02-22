pipeline {
  agent any
  parameters {
    run description: '', filter: 'SUCCESSFUL', name: 'RUN', projectName: 'joost/demomon4/devoptics-build/master'
  }
  stages {
    stage('Build') {
      steps {
        echo "Going to consume: devoptics-build-${RUN_NUMBER}"
        devOpticsConsumes file: '', id: "devoptics-build-${RUN_NUMBER}", 
          jobName: "${RUN_JOBNAME}",
          masterUrl: '', runId: "${RUN}", type: 'demo'
      }
    }
  }
}
