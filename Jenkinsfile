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

    stage('maven-build') {
      parallel {
        stage('maven-build') {
          steps {
            sh 'mvn clean install'
          }
        }

        stage('maven validate') {
          steps {
            sh 'mvn validate'
          }
        }

      }
    }

    stage('sonar-qualitychecks') {
      steps {
        sh 'mvn sonar:sonar'
      }
    }

  }
}