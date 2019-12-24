pipeline {
     agent {
        
        label {
            label "master"
             customWorkspace "/home/rknowsys/.jenkins/EurekaServer"
              }
        }
     
    stages {
    stage('BuildAndPackage') { 
            steps {
           
            echo '-----------------build maven clean install----------------'
            sh 'cd /home/rknowsys/.jenkins/EurekaServer/EurekaServer1/'
            sh 'mvn clean install'
               }
            }
   
    stage('Deploy') {
       
            steps {
                 sh 'cd /home/rknowsys/.jenkins/EurekaServer/EurekaServer1/target/'
                 sh 'export BUILD_ID=dontKillMe'
                 sh 'nohup java -Dserver.port=9000 -jar EurekaServer1-0.0.1-SNAPSHOT.jar &'
         }
       }
   
    }
  
  
}
