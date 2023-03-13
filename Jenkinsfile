pipeline {
    agent any

    stages {
        stage('Code Checkout: SCM') {
            steps {
                git credentialsId: 'git_credentials', url: 'https://github.com/cheerlavamsi/kubernetes.git'
            }
        }
    }
}

