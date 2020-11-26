pipeline {
   agent any

   tools {
      maven "maven"
   }

   stages {
      stage('Deploy Test API') {
         steps {
            sh "mvn clean exec:java"
         }
      }
   }
}
