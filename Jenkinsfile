pipeline {
    agent any
    environment {
        PROJECT_ID = 'g-prj-afts-cs-uni-pro'
        CLUSTER_NAME = 'g-clt-afts-uni-prod'
        LOCATION = 'europe-west3'
        CREDENTIALS_ID = 'g-prj-afts-cs-uni-pro'
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
