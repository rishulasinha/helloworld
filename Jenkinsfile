pipeline {
    agent any
	
    stages {
        stage('Hello') {
            steps {
		git credentialsId: '7af48099-1db5-4eb9-9e1d-ffcc3d371f9f', url: 'https://github.com/rishulasinha/helloworld.git'
                bat 'echo "Hello"'
		    
		javac Hello.java
		java Hello
		
            }
        }
	    stage('emailNotification'){
		    steps{
			    emailext ( 
		       subject: "Job Build", 
		       body: "Job Build Success.${env.JOB_NAME} [${env.BUILD_NUMBER}]",
		       to: "rishulasinha13@gmail.com"
		     )
		    }
	    }
    }
}