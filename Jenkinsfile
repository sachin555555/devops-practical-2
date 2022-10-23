pipeline {
    agent any
	

 stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/sachin555555/devops-practical-2.git'
             
          }
        }
       

  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t devops9class:latest .' 
                sh 'docker tag devops9class sachin555555/devops9class:$BUILD_NUMBER'
               
          }
        }
  stage('Publish image to Docker Hub') {
            steps {
        withDockerRegistry([ credentialsId: "DokerHub", url: "" ]) {
           sh  'docker push sachin555555/devops9class:$BUILD_NUMBER' 
		}
                  
          }
        }
		
    }
}
