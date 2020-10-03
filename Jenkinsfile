pipeline {
  agent any
  stages {
    stage('Git-Cred') {
      steps {
        git(url: 'https://github.com/MohitBhardwaj1998/Go-Party.git', branch: 'master', credentialsId: 'github_Cred')
        echo 'Successfully connected'
      }
    }
    stage('Git-Clone') {
     sh 'git clone https://github.com/MohitBhardwaj1998/Go-Party.git' 
         echo 'Successfully cloned'
    } 

  }
}
