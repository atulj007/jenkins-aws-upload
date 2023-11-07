pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'ap-south-1',credentials:'aws-cred') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(bucket:'vprofile-build-artifact',file:'app.py' )
                  }
              }
         }
     }
}
