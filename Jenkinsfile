pipeline {
  agent any
  environment { 
    PROJECT_ID = 'enduring-art-312620'
    CLUSTER_NAME = 'jenkins-k8s-demo-cl' 
    LOCATION = 'europe-west2-a'
    CREDENTIALS_ID = 'kubernetes'
  }
  
  stages {
    stage ("echo") {
      steps {
        echo "hello"
        sleep 30
      }
    }
  }
}
