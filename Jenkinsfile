pipeline {
   agent any

   stages {
      stage('Import API to Axway API Manager') {
         steps {
            
             withMaven(maven: 'maven') {
                    sh 'mvn clean exec:java'
              }
     
         }
      }
   }
}
