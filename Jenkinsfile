pipeline {
    agent {
    node {
        label 'k8s' //set your kubernetes node
    }
}
   
  stage('Deploying db to Kubernetes') {
      steps {
        script {
          
          kubernetesDeploy(configs: "mysql_pod.yml", kubeconfigId: "kubernetes")
        }
      }
    }
    stage('Deploying wp to Kubernetes') {
      steps {
        script {
          kubernetesDeploy(configs: "wp_php_apache_pod.yml", kubeconfigId: "kubernetes")
        }
 }
}
}
