pipeline {
    agent {
    node {
        label 'k8s' //set your kubernetes node
    }
}
   
  stages {
     stage('Preparation') {
        steps {
           cleanWs()
         git credentialsId: 'Access_github', url: "https://github.com/pkupryianau/Labk8s"
        }
   }
  stage('Build') {
     steps {
        sh 'echo No build required for Gateway'
     }
  }
  stage('Deploy to Cluster') {
    steps {
      sh 'kubectl create -f mysql_pod.yml --record=true'
    }
  }
 }
}
