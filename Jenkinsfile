pipeline{
    agent{ label  'maven' } 
    parameters{
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'origin/devlop', name: 'BRANCH', type: 'PT_BRANCH'
        gitParameter name: 'TAG',type: 'PT_TAG', selectedValue: 'NONE'       
        
    }
    stages{
        stage ('fea') {
            tools{ maven 'MAVEN_HOME' }
            when { 
                expression { BRANCH == 'origin/feauture1' || BRANCH == 'feauture1'  }
            }
            steps{
                echo '========sonar============='
            }
        }        
        stage ('dev') {
            tools{ maven 'MAVEN_HOME' }
            when { 
                expression { BRANCH == 'origin/devlop' || BRANCH == 'devlop'  }
            }
            steps{
                sh 'mvn validate'
                echo '=====================ws==devaaaaaaaaaaaaa====================================='
                sh 'mvn compile'
                sh 'mvn test'
            }
        }

        stage ('QA'){
            tools{ maven 'MAVEN_HOME' }
            when {
                expression { BRANCH == 'origin/release' || BRANCH == 'release'  }
            }
            steps{ 
                   echo '=====QA========='
            }
        }
        
        
    }
}
