pipeline {
  agent any
   
  triggers {
         pollSCM('* * * * *')
     }
  
  timeout(time: 5, unit: 'DAYS'){
     input 'Do you want to proceed with the Deployment?'
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
