pipeline {
  agent any
  stages {
    stage('Git-Checkout') {
      steps {
        git(url: 'https://github.com/MohitBhardwaj1998/Go-Party.git', branch: 'master', credentialsId: 'github_Cred')
       
        echo 'Successfully connected'
      }
    } 
    stage('Build Docker Image') {
      steps{
         
          sh 'docker build -t MohitBhardwaj1998/nginx:2.0.0 .'
        
      }
   
    } 

  }
}
 
