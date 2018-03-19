pipeline {
  agent any
   
  triggers {
         pollSCM('* * * * *')
     }
  options{
     timeout(time: 2, unit: 'DAYS')
  }
  stages{
        stage('Build'){          
            steps {
                input 'Do you want to proceed to the Deployment?'
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
