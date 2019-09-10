//test
pipeline{
    agent any
    
    stages{
        stage("Stage1") {
            steps{
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage("Testing Stage"){
            steps{
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn test'
                }
            }
        }
    }
}