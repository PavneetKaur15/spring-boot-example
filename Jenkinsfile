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
     post
    {
       always{
            mail to: 'pavneet.kaur@knoldus.com',
			subject: "Pipeline: ${currentBuild.fullDisplayName} is ${currentBuild.currentResult}",
			body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}"
        }
}
