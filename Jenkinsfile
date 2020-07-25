pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path. Demo comment
      maven "maven"
      jdk "java"
                
   }

   stages {
      stage('Get Code') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/sidvijay18/tomcat_pipeline.git'   
         }

      }
      
      
      stage('Code Build') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn package"
         }

      }
      
      stage('Code Deploy') {
         steps {
        
            // To run Maven on a Windows agent, use
           bat label: '', script: 'copy /Y target\\tomcat-1.0.war E:\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps'
         }

      }
   }
}
