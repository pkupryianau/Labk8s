pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/pkupryianau/Labk8s.git'
      }
    }
    agent {
    kubernetes {
      yamlFile 'mysql_pod.yml'
    }
  }
    stage('Deploying db to Kubernetes') {
      steps {
        script {
          sh 'kubernetesDeploy(configs: "mysql_pod.yml", kubeconfigId: "kubernetes")'
        }
      }
    }
    stage('Deploying wp to Kubernetes') {
      steps {
        script {
          sh 'kubernetesDeploy(configs: "wp_php_apache_pod.yml", kubeconfigId: "kubernetes")'
        }
      }
    }

  }

}

