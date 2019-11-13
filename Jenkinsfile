//test example
//another example
pipeline{
    agent any
    
    stages{
        stage("mvn clean") {
            steps{
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage("mvn test"){
            steps{
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn test'
                }
            }
        }
    }
}