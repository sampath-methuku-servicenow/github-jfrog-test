pipeline {
    agent any
stages {

               
         stage('Build-Step') {
             when {
               branch 'pr_branch'                  
             }
             steps {
                     echo 'Build Step '
             }
         }
     

        stage('Change-Step') {
              steps {
                   echo 'Change Step'
                  // snDevOpsChange()
              }
        }
}
   
}
