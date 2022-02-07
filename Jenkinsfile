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
    post {
        always {
            emailext body: 'A Test Email', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
