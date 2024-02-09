pipeline {
    agent any
    environment {
        // Define the interval in minutes
        SCHEDULE_INTERVAL = '2'
    }
	triggers {
        cron('H/2 * * * *')  // Run every 2 minutes
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

        stage('Wait for Next Run') {
            steps {
                script {
                    currentBuild.result = 'ABORTED'  // Abort the current build
                    echo "Waiting for the next run in ${SCHEDULE_INTERVAL} minutes..."
                    sleep(time: 60 * SCHEDULE_INTERVAL as Integer, unit: 'SECONDS')  // Wait for the next run
                    input message: 'Manually triggered', submitter: 'auto-trigger'  // Manual input to proceed
                }
            }
        }   

    }
}

