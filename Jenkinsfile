pipeline {
   agent any
   
    parameters {
        string(name: 'host', description: 'API Manager Host Name', defaultValue: 'https://forrester.demo.axway.com:8075')
        string(name: 'username', description: 'API Manager Administrator Username', defaultValue: 'apiadmin')
        password(name: 'password', description: 'API Manager Administrator Password')
        string(name: 'stage', description: 'Targer Environment to Deploy', defaultValue: 'dev')
       
    }

   stages {
      stage('Import API to Axway API Manager') {
         steps {
            
             withMaven(maven: 'maven') {
                sh 'mvn clean exec:java -Dexec.args="-h ${host} -u ${username} -p ${password} -c ./api-definition/1-design-only-config.json -s api-env -f true"'
              }
     
         }
      }
   }
}
