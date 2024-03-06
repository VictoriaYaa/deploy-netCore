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
                    withKubeConfig([credentialsId: kubeConfig]){
                        sh """
                        kubectl apply -f deployment-backend.yaml
                        kubectl apply -f deployment-frontend.yaml
                        """
                        println "=========== Successfully deployed the Web Application to default NS ============"
                    }
                }
            }
        }
        stage("Deploy netCore Web Application to a different NS") {
            steps {
                script {
                    withKubeConfig([credentialsId: kubeConfig]){
                        sh """
                        kubectl apply -f deployment-backend.yaml -n ${params.namespace}
                        kubectl apply -f deployment-frontend.yaml -n ${params.namespace}
                        """
                        println "=========== Successfully deployed the Web Application to ${namespace} NS ============"
                    }
                }
            }
        }
    }
}


