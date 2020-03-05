pipeline{
    agent{ label  'maven' } 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/devlop', name: 'BRANCH', type: 'PT_BRANCH'
        gitParameter name: 'TAG',type: 'PT_TAG', selectedValue: 'NONE'
    }
    stages{
        stage ('dev') {
            tools{ maven 'MAVEN_HOME' }
            when { 
                expression {BRANCH == 'devlop'  }
            }
            steps{
                sh 'mvn validate'
                sh 'mvn compile'
                sh 'mvn test'
                sh 'mvn sonar:sonar'
            }
        }

        stage ('QA'){
            tools{ maven 'MAVEN_HOME' }
            when {
                expression {TAG == '2.0.0'  }
            }
            steps{
                   sh 'mvn install' 
            }
        }
        
        
    }
}
