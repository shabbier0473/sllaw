pipeline{
    agent any
    stages{
        stage ('build master'){
            when {
                branch 'master'
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
        stage ('build release'){
            when {
                branch 'release'
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

