pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('master') {
        when {
            expression {GIT_BRANCH == 'origin/master'  }
        }
      steps {
        echo "hello master"
      }
    }
    stage('release') {
        when {
            expression {GIT_BRANCH == 'origin/release'  }
        }
      steps {
        echo "hello release"
      }
    }
  }
}
