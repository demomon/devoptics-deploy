pipeline {
  agent any
  parameters {
    run description: '', filter: 'SUCCESSFUL', name: 'RUN', projectName: '../../devoptics-build/master'
  }
  stages {
    stage('Build') {
      steps {
        // a run parameter will add _JOBNAME and _NUMBER as additional environment variables
        echo "Going to consume: devoptics-build-${RUN_NUMBER}"
        gateConsumesRun jobName: "${RUN_JOBNAME}", runId: "${RUN}"

        // deprecated steps as of February 2019
        //devOpticsConsumes file: '', id: "devoptics-build-${RUN_NUMBER}", 
        //  jobName: "${RUN_JOBNAME}",
        //  masterUrl: '', runId: "${RUN}", type: 'demo'
      }
    }
  }
}
