pipeline{
    agent {label 'maven' } 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages{
        stage ('master') {
            when { 
                expression {BRANCH == 'master'  }
            }
            tools { maven 'MAVEN_HOME' }
            steps{
                sh 'mvn validate'
            }
        }
        stage ('release'){
            when {
                expression {BRANCH == 'release'  }
            }
            tools { maven 'MAVEN_HOME' }
            steps{
                   sh 'mvn install' 
                }
        }
    }
}
