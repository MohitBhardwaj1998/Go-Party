 def dockerRun = "docker build -t mohitbhardwaj/nginx:2.0.0 ."
def dockerPush = "docker push mohitbhardwaj/nginx:2.0.0"
dockerrunner = "docker run -p 8080:8080 -d mohitbhardwaj/nginx:2.0.0"
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
			
		 
		  sh "ssh -o StrictHostKeyChecking=no centos@52.15.59.200 ${dockerRun}"
		   sh "ssh -o StrictHostKeyChecking=no centos@52.15.59.200 ${dockerPush}"
		}
		
      }
	     
    } 
	 stage('docker deploy') {
      steps{
         sshagent(['zabbix']) {
		 
		  sh "ssh -o StrictHostKeyChecking=no centos@18.221.21.201 ${dockerrunner}"			
			}
      }
   
    } 

  }
}
 
