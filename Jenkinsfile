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
         git credentialsId: '674ad01b-b249-4a9d-9145-a2cf86fe8214', url: "https://github.com/pkupryianau/Labk8s"
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
