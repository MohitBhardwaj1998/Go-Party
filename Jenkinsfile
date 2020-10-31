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
	  sshagent(['centos-user']) {
			
		  def dockerRun = 'docker build -t mohitbhardwaj/nginx:2.0.0 .'
		  def dockerPush = 'docker push mohitbhardwaj/nginx:2.0.0'
		  sh "ssh -o StrictHostKeyChecking=no centos@3.15.137.204 ${dockerRun}"
		   sh "ssh -o StrictHostKeyChecking=no centos@3.15.137.204 ${dockerPush}"
		}
		
      }
	     
    } 
	 stage('docker deploy') {
      steps{
         sshagent(['zabbix']) {
		 dockerRun = 'docker run -p 8080:8080 -d mohitbhardwaj/nginx:2.0.0'
		  sh "ssh -o StrictHostKeyChecking=no centos@18.221.21.201 ${dockerRun}"			
			}
      }
   
    } 

  }
}
