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
                deploy adapters: [tomcat9(credentialsId: 'b62cda21-84dc-4188-8e01-9b4d2d78dfe7', path: '', url: 'http://172.31.3.91:8080/')], contextPath: 'testapp', war: '**/*.war'
            }
        }
       }
}
