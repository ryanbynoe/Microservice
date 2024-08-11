pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetess') {
            steps {
                kubeconfig(credentialsId: 'k8-token', serverUrl: 'https://43314C0861EAA75D943EC6183BF28E81.gr7.us-east-1.eks.amazonaws.com') {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                kubeconfig(credentialsId: 'k8-token', serverUrl: 'https://43314C0861EAA75D943EC6183BF28E81.gr7.us-east-1.eks.amazonaws.com') {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
