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
                    sh "mvn -B -DskipTests clean package"
                }
                
            }
            stage("Test")
            {
                steps{
                    sh "mvn test"
                }
            }
      }
}
