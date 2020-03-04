pipeline{
    agent any 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
        gitParameter name: 'TAG',type: 'PT_TAG', selectedValue: 'NONE'
    }
    stages{
        stage ('master') {
            when { 
                expression {GIT_BRANCH == 'origin/master'  }
            }
            tools { maven 'MAVEN_HOME' }
            steps{
                sh 'mvn clean install'
            }
        }
        stage ('release'){
            when {
                expression {GIT_BRANCH == 'origin/release'  }
            }
            tools { maven 'MAVEN_HOME' }
            steps{
                    echo 'release' }
        }
    }
}
