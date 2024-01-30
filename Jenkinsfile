@Library('cicd')_
pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload')
        {
            steps
            {
                script
                {
                    try
                    {
                     lib.gitdownload("myrepo")
                    }
                    catch(Exception e){
                        mail bcc: '', body: 'Git not downloaded', cc: '', from: '', replyTo: '', subject: 'continous download not working', to: 'ab@gmail.com'
                        exit(1)
                    }
                }
            }    
        }
         stage('ContinousBuild')
        {
            steps
            {
                script
                {
                    try
                    {
                       lib.gitbuild()
                    }
                    catch(Exception e2){
                         mail bcc: '', body: 'artifacts not created', cc: '', from: '', replyTo: '', subject: 'continous build not working', to: 'ab@gmail.com'
                    }
                }
            }
        }
          stage('ContinousDeploy')
        {
            steps
            {

                script
                {
                    try
                    {
                      lib.gitdeploy("SharedLibrary1","18.190.207.36","testing.war")
                    }
                    catch(Exception e3){
                      mail bcc: '', body: 'deployment', cc: '', from: '', replyTo: '', subject: 'continous deploy not working', to: 'ab@gmail.com'   
                    }
                }
          
            }
        }
    }
}

