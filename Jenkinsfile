pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('master') {
        when {
            git branch: "${params.BRANCH}" == 'origin/master'  
        }
      steps {
        echo "hello master"
      }
    }
    stage('release') {
        when {
            git branch: "${params.BRANCH}" == 'origin/release' 
        }
      steps {
        echo "hello release"
      }
    }
  }
}
