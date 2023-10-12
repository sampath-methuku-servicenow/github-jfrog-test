pipeline {
    agent any
stages {

           
         stage('Build-Step') {
 
             steps {
                     echo 'Build Step 23 '
                 snDevOpsArtifact artifactsPayload: '{"artifacts":[{"name": "sa-web.jar", "version": "1.9", "repositoryName": "services-1031"}, {"name": "sa-db.jar", "version": "1.3.2", "repositoryName": "services-1032"}], "branchName": "main"}'
                 snDevOpsPackage artifactsPayload: '{"artifacts":[{"name": "sa-web.jar", "version": "1.9", "repositoryName": "services-1031"}, {"name": "sa-db.jar", "version": "1.3.2", "repositoryName": "services-1032"}], "branchName": "main"}', name: 'packageName'
             }
         }
     

        stage('Change-Step') {
              steps {
                   echo 'Change Step'
                   snDevOpsChange()
              }
        }
}
   
}
