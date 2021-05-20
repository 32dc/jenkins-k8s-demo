pipeline {
  agent any
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
        kubernetesDeploy configs: 'pod.yml', kubeConfig: [path: ''], kubeconfigId: 'k8s-config', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
      }
    }
  }
} 
