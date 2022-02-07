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
            mail to: 'pavneet.kaur2415@gmail.com',
			subject: "Jenkins Pipeline Status",
			body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}"
        }
    }
}
