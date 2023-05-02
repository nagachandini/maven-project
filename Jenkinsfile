pipeline {
  agent {
    node {
      label 'demo_node'
    }

  }
  stages {
    stage('git checkout') {
      steps {
        git(url: 'https://github.com/nagachandini/maven-project.git', branch: 'master', credentialsId: 'git_token')
      }
    }

  }
}