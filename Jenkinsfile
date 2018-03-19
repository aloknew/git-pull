pipeline {
  agent any
   
  triggers {
         pollSCM('* * * * *')
     }
  
  stages{
        stage('Deploy approval'){
              input "Deploy to prod?"
        }
    
        stage('Build'){
            steps {
                sh 'echo done'
                }
         }
         
        stage ('Deploy to Production'){
              steps {
                  sh '/usr/local/bin/sshput -u enabler -f SERVER_LIST *.html /opt/app/workload/httpserver/htdocs/rtapi/'
                  }
         }
   }
}
