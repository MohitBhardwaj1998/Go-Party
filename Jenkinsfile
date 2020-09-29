pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'first pipeline'
      }
    }

    stage('Git-to-Live') {
      steps {
        git(url: 'https://github.com/MohitBhardwaj1998/Go-Party.git', branch: 'master', credentialsId: 'github_Cred')
      }
    }

  }
}
