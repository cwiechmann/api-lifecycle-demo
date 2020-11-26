pipeline {
   agent any

   tools {
      maven
   }

   stages {
      stage('Deploy Test API') {
         steps {
            sh "mvn clean exec:java"
         }
      }
   }
}
