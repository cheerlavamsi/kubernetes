pipeline {
    agent any

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

