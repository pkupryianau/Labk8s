pipeline {
agent any
    environment {
   	 PROJECT_ID = 'jenkins_k8s'
            	CLUSTER_NAME = 'k8s'
            	CREDENTIALS_ID = 'kubernetes'
    }
    
stages {
    	stage('Checkout') {
   	 	steps {
   		 	checkout scm
   	 	}
    	}
    	 						 	 
   	 	}
    	}
   
    	stage('Deploy to K8s') {
   	 	steps{
   		 	echo "Deployment started ..."
   		 	sh 'ls -ltr'
   		 	sh 'pwd'
   		 	sh "sed -i ('s/pipeline:latest/pipeline:class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID,clusterName: env.CLUSTER_NAME,manifestPattern: 'mysql_pod.yml',credentialsId: env.CREDENTIALS_ID,verifyDeployments: true])''\n''
   			 }
   		 }
   	 }    
}
