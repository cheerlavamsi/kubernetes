pipeline {
    agent any
	triggers {
        	cron('43 14 * * 3')  // Run every Wednesday at 12:25 PM
    	}

    stages {
        stage('Code Checkout: SCM') {
            steps {
                git branch: 'main', credentialsId: 'Git_Access', url: 'https://github.com/cheerlavamsi/kubernetes.git'
            }
        }
        
	stage('Build') {
	    steps {
	        echo 'hello'
	    }
	}    

    }
}

