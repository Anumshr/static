pipeline{
	agent any
	stages{
		stage('Build'){
			steps {

				sh 'echo "Hello -world "'
				sh '''
						echo "Multi line shell"
					'''

			}
		}
		stage('Upload to AWS'){
			steps{
	    		withAWS(region:'us-west-2',credentials:'aws-static'){
	    		s3Upload(bucket: 'myawsbucket-anukriti', pathStyleAccessEnabled: false, includePathPattern: 'index.html')
	    		}
	    	}
		}

	}
}
