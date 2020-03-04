pipeline{
    agent { label 'maven'}
    parameters{
        gitParameter branchFilter: 'origin/*', name: 'BRANCH', type: 'PT_BRANCH'
    }   
    stages{
        stage('master'){
            when {
                expression { GIT_BRANCH == 'origin/master'  }
            }
            steps{
                echo "master"
            }
        }
        stage ('release'){
            when {
                expression { GIT_BRANCH == 'origin/release'  }
            }
            steps{
                echo "release"
            }                
            
        }
    }
}
