pipeline{
    agent maven 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages{
        stage ('validate') {
            when { 
                expression {BRANCH == 'develop'  }
            }
            steps{
                sh 'mvn validate'
            }
        }
        stage ('compile'){
            when {
                expression {BRANCH == 'develop'  }
            }
            steps{
                   sh 'mvn compile' 
                }
        }
       stage ('test'){
            when {
                expression {BRANCH == 'develop'  }
            }
            steps{
                   sh 'mvn test' 
                }
        }
        
    }
}
