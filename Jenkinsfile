pipeline {
  agent any
   
  triggers {
         pollSCM('* * * * *')
     }
  
  stages{
        stage('Build'){
          options{
            timeout(time: 2, unit: 'DAYS') {
            input 'Do you want to proceed to the Deployment?'
            }
          } 
            steps {                
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
