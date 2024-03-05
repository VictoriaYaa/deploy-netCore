pipeline {
  agent  {
    label 'build||linux'
  }
  parameters {
    text name: 'namespace', defaultValue: 'default' , description: 'Choose namespace to deploy the Web Application'  
    }
  stages {
    stage("Deploy netCore Web Application") {
      steps {
        script {
            withKubeConfig([serverUrl: 'https://192.168.49.2']) {
                sh "kubectl get pod -n ${params.namespace}"
                println "=========== Successful${namespace} ============"
                }
                }
            }
        }
    }
}


