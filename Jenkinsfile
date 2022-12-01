pipeline {
    agent {
    node {
        label 'minikube' //set your kubernetes node
    }
}
   environment {
     ORGANIZATION_NAME = "pkupryianau"
     YOUR_DOCKERHUB_USERNAME = "pkupryianau" (optional)
     SERVICE_NAME = "Labk8s"
REPOSITORY_TAG="${YOUR_DOCKERHUB_USERNAME}/${ORGANIZATION_NAME}-${SERVICE_NAME}:${BUILD_ID}"
   }

   stages {
     stage('Preparation') {
        steps {
           cleanWs()
         git credentialsId: '674ad01b-b249-4a9d-9145-a2cf86fe8214', url: "https://github.com/${ORGANIZATION_NAME}/${SERVICE_NAME}"
        }
   }
  stage('Build') {
     steps {
        sh 'echo No build required for Gateway'
     }
  }

  
  } 
  }
  stage('Deploy to Cluster') {
    steps {
      sh 'kubectl create -f mysql_pod.yml --record=true'
    }
  }
 

