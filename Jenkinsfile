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
         git credentialsId: 'GitHub_01122022', url: "https://github.com/pkupryianau/Labk8s"
        }
   }
  
  stage('Deploy to Cluster') {
    steps {
      sh 'kubectl create -f mysql_pod.yml --record=true'
    }
  }
 }
}
