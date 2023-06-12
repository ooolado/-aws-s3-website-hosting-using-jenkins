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
                  withAWS(region:'us-east-1',credentials:'b325d6ca-2f32-414a-99bc-fd838506700a') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'donporosky.click')
                         s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'components.html', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js.gz', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'assets', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'sample', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.map', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css', bucket:'donporosky.click')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css.gz', bucket:'donporosky.click')
                       
                     
                  }
              }
         }
     }
}
