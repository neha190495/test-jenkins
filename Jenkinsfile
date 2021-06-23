pipeline {
    agent { label 'jnlp-slave' }
    stages{
        stage('Checkout Source'){
            steps{
                git url:'https://github.com/neha190495/test-jenkins.git', branch:'main'
            }
        }
        stage('Deploy to Kubernetes'){
            steps{
                script {
                    kubernetesDeploy(configs: "node-server.yaml", kubeconfigId: "mykubeconfig")
                }
            }
        }
    }
}
