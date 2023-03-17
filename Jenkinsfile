pipeline {
    agent any
    stages {
        stage('Upload') {
            steps {
                script { 
                     def server = Artifactory.server 'JFROG1'
                     def uploadSpec= """{
                        "files": [{
                           "pattern": "/Volumes/E/WORK/code/app-devops-jenkins/target/app-devops-*.jar",
                           "target": "default-docker-virtual/"
                        }]
                     }"""

                    def buildInfo = server.upload(uploadSpec) 
                    server.publishBuildInfo buildInfo   
                }}
        }
        
        stage('Download') {
            steps {
                script { 
                    def server = Artifactory.server 'JFROG1'       
                    def downSpec= """{
                            "files": [{
                               "pattern": "default-docker-local/app-devops*.jar",
                               "target":"/tmp/"
                            }]
                         }"""

                    def buildInfo2 = server.download(downSpec) 
                    server.publishBuildInfo buildInfo2   
                    
                }}
            }
        
        
        
    }
    
}
