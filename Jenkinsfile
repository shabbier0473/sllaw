pipeline{
    agent any
    parameters{
         gitParameter branchFilter: 'origin/*', defaultValue: 'origin/master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages{
        stage ('master'){
            when {
                branch 'origin/master'
            }
            tools{
                maven 'MAVEN_HOME'
                jdk 'JAVA_HOME'
            }
            steps{
                timestamps{
                 echo '========master======='
                 sh 'mvn install' 
                }
               
            }
        }
        stage ('release'){
            when {
                branch 'origin/release'
            }
            tools{
                maven 'MAVEN_HOME'
            }
            steps{
                echo '======release========='
                sh 'mvn install'
            }
        }
        stage ('tag build'){
            when {
                buildingTag()
            }
            steps{
                sh 'mvn test'
                echo "=====tag building===="
            }
        }
    }
}
