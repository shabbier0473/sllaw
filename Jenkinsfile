pipeline {
    agent any
    parameters {
        gitParameter branchFilter: 'origin.*/(.*)', defaultValue: 'master', name: 'BRANCH_A', type: 'PT_BRANCH', useRepository: '.*exampleA.git'
        gitParameter branchFilter: 'origin.*/(.*)', defaultValue: 'master', name: 'BRANCH_B', type: 'PT_BRANCH', useRepository: '.*exampleB.git'
        
    }
    stages {
        stage('Example') {
            steps {
                git branch: "${params.BRANCH_A}", url: 'https://github.com/klimas7/exampleA.git'
                git branch: "${params.BRANCH_B}", url: 'https://github.com/klimas7/exampleB.git'
            }
        }
    }
}
