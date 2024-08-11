pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {) 
                kubeconfig(credentialsId: 'k8-token', serverUrl: 'https://43314C0861EAA75D943EC6183BF28E81.gr7.us-east-1.eks.amazonaws.com'  sh "kubectl apply -f deployment-service.yml"
                    sleep 60{
                   
                }
                echo 'Deployment applied and waiting for 60 seconds'
            }
        }

        stage('Verify Deployment') {
            steps {
                kubeconfig(credentialsId: 'k8-token', serverUrl: 'https://43314C0861EAA75D943EC6183BF28E81.gr7.us-east-1.eks.amazonaws.com') sh "kubectl get all -n webapps"{
                   
                }
                echo 'Deployment verification completed'
            }
        }
    }
}
