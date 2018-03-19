pipeline {
  agent any
   
  triggers {
         pollSCM('* * * * *')
     }
  
  stages{
        stage('Build'){
            steps {
                input "Deploy to prod?"
                sh 'echo APPROVED'
                }
         }
         
        stage ('Deploy to Production'){
              steps {
                  sh '/usr/local/bin/sshput -u enabler -f SERVER_LIST *.html /opt/app/workload/httpserver/htdocs/rtapi/'
                  }
         }
   }
}
