pipeline{
    agent any
    tools { 
        maven 'Maven 3.8.4'
    }
    stages
       {
           stage("Build")
            {
                steps{
                    sh "mvn compile"
                }
                
            }
            stage("Clean")
            {
                steps{
                    sh "mvn clean"
                }
            }
            stage("Test")
            {
                steps{
                    sh "mvn test"
                }
            }
            stage("Package")
            {
                steps{
                    sh "mvn package"
                }
            }
      }
}
