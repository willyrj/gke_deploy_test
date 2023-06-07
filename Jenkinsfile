pipeline {
    agent any
    environment {
        PROJECT_ID = 'testing01-387705'
        CLUSTER_NAME = 'cluster-1'
        LOCATION = 'us-central1'
        CREDENTIALS_ID = '<YOUR_CREDENTIAS_ID>'
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'nginx-deployment.yaml',
                credentialsId: env.CREDENTIALS_ID,
                verifyDeployments: true])
            }
        }
    }
}
