//test example
//another example
pipeline{
    agent any
    
    stages{
        checkout scm
      def lastSuccessfulCommit = getLastSuccessfulCommit()
      def currentCommit = commitHashForBuild( currentBuild.rawBuild )
      if (lastSuccessfulCommit) {
        commits = sh(
          script: "git rev-list $currentCommit \"^$lastSuccessfulCommit\"",
          returnStdout: true
        ).split('\n')
        println "Commits are: $commits"
      }
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
