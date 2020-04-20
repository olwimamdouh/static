pipeline {
     agent any
     stages {
         stage('Upload to AWS') {
             dir ('/home/olwi/Downloads/cloud-devops-nd/Jenkins-Pipelines-on-AWS/static/') {
		     pwd();
		     withAWS(region:'us-east-1',credentials:"aws-static") {
		          def identity=awsIdentity();


        		  s3Upload(file:'index.html', workingDir:'dist', includePathPattern:'**/*)
                    }
                    sh 'echo "Hello World"'
                    sh '''
                        echo "Multiline shell steps works too"
                        ls -lah
                    '''
                  };

            }
        
      }
}

