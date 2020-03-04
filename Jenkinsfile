pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('master') {
        when {
            branch 'origin/master' 
        }
      steps {
        echo "hello master"
      }
    }
    stage('release') {
        when {
            branch 'origin/release'
        }
      steps {
        echo "hello release"
      }
    }
  }
}
