pipeline{
    agent{ label  'maven' } 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages{
        stage ('validate') {
            when { 
                expression {BRANCH == 'devlop'  }
            }
            steps{
                sh 'mvn validate'
            }
        }
        stage ('compile'){
            when {
                expression {BRANCH == 'devlop'  }
            }
            steps{
                   sh 'mvn compile' 
                }
        }
       stage ('test'){
            when {
                expression {BRANCH == 'devlop'  }
            }
            steps{
                   sh 'mvn test' 
                }
        }
        
    }
}
