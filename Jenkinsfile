pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload')
        {
            steps
            {
               git 'https://github.com/Saimahi24/myrepo.git' 
            }
        }
         stage('ContinousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
          stage('ContinousDeploy')
        {
            steps
            {
                input message: 'Need for approval', submitter: 'vengala,abc'
              sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@18.117.75.184:/var/lib/tomcat9/webapps/testing.war'
            }
        }
    }
}
