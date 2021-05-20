pipeline {
  agent any
  environment { 
    PROJECT_ID = 'enduring-art-312620'
    CLUSTER_NAME = 'jenkins-cl'
    NAMESPACE = 'jenkins-ns'
    LOCATION = 'europe-west2-a'
    CREDENTIALS_ID = 'kubernetes'
  }
  
  stages {
    stage ("Git Clone") {
      steps {
        git branch: 'main', credentialsId: '4a0a0b13-b4c9-4a99-a64b-ecd948649d72', url: 'https://github.com/32dc/jenkins-k8s-demo.git'
        echo "GitHub repo cloned..."
      }
    }
    stage ("Deploy K8s") {
      steps {
        echo 'starting k8s...'
        kubernetesDeploy credentialsType: 'KubeConfig', kubeConfig: [path: '/var/lib/jenkins/workspace/.kube/config'], configs: 'pod.yml', kubeconfigId: 'k8s-config', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '']
      }
    }
  }
} 
