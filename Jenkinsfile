pipeline {
  agent any
  
  parameters {
    string(name: 'tomcat_dev', defaultValue: '35.166.210.154', description: 'Staging Server')        
    string(name: 'tomcat_prod', defaultValue: '34.209.233.6', description: 'Production Server')   
    } 
  
  stages{
        stage('Build'){
            steps {                
                sh 'echo done'            
                }        
         }
         
        stage ('Deploy to Production'){
              steps {                    
                  sh 'ls -ltr'
                  }            
         }
   }
}
