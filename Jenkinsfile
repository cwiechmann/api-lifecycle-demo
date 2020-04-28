pipeline {
   agent any
   
   tools {
     
      maven "maven"
   }
   
    parameters {
        string(name: 'host', description: 'API Manager Host Name', defaultValue: 'forrester.demo.axway.com')
        string(name: 'stage', description: 'Targer Environment to Deploy', defaultValue: 'apim-dev')
       
    }

   stages {
      stage('Import API to Axway API Manager') {
         steps {
            
            withCredentials([usernamePassword(credentialsId: "${stage}", usernameVariable: 'username', passwordVariable: 'password')])  {
                sh 'mvn clean exec:java -Dexec.args="-h ${host} -u ${username} -p ${password} -c ./api-definition/1-design-only-config.json -s api-env -f true"'
              }
     
         }
      }
   }
}
