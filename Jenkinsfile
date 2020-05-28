pipeline {
  agent none
  parameters {
    run description: 'Run for Build', filter: 'SUCCESSFUL', name: 'RUN', projectName: 'devoptics/devoptics-build/master'
    // we could directly consume the job run, or, consume the artifact via `withMaven`
    // string defaultValue: '', description: 'Manually enter Run ID for lib-build', name: 'LIB_RUN_ID', trim: true
  }
  stages {
    stage('Deply') {
      steps {
        echo 'deploying ...'
      }
    }
    stage('DevOptics Sync') {
      steps {
        // a run parameter will add _JOBNAME and _NUMBER as additional environment variables
        echo "Going to consume: devoptics-build-${RUN_NUMBER}"
        gateConsumesRun jobName: "${RUN_JOBNAME}", runId: "${RUN}"
        
        // echo "And going to consume: devoptics-lib-build-${LIB_RUN_ID}"
        // gateConsumesRun jobName: "devoptics/devoptics-lib-build/master", runId: "${LIB_RUN_ID}"
      }
    }
  }
}
