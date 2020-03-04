pipeline{
    agent maven 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages{
        stage ('master') {
            when { 
                expression {BRANCH == 'master'  }
            }
            steps{
                sh 'mvn validate'
            }
        }
        stage ('release'){
            when {
                expression {BRANCH == 'release'  }
            }
            steps{
                   sh 'mvn install' 
                }
        }
    }
}
