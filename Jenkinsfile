pipeline {
    agent {
    node {
        label 'k8s' //set your kubernetes node
    }
}
    stages { 
  stage('Deploying db to Kubernetes') {
      steps {
        sh 'kubectl create -f mysql_pod.yml'
        }
      }
    }
    stage('Deploying wp to Kubernetes') {
      steps {
        sh 'kubectl create -f wp_php_apache_pod.yml'
        }
   }
  }
 }
}
