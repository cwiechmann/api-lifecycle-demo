pipeline {
   agent any
   
   tools {
     
      maven "maven"
   }
   
    parameters {
        string(name: 'host', description: 'API Manager Host Name', defaultValue: 'forrester1.demo.axway.com')
        string(name: 'stage', description: 'Targer Environment to Deploy', defaultValue: 'dev')
        string(name: 'returnCodeMapping', description: 'Swagger Promote CLI return code mapping', defaultValue: '10:0')
       
    }

   stages {
      stage('Import API to Axway API Manager') {
         steps {
            script{
               def props = readJSON file: 'api-definition/4-complete-config.json'
               print props
               def tags = props.get("tags")
               print tags
               print tags.getClass().getName()
            }
            
            withCredentials([usernamePassword(credentialsId: "${stage}", usernameVariable: 'username', passwordVariable: 'password')])  {
                sh 'mvn clean exec:java -Dexec.args="-h ${host} -u ${username} -p ${password} -c ./api-definition/4-complete-config.json -s api-env -f true -returnCodeMapping ${returnCodeMapping}"'
              }
     
         }
      }
   }
}
