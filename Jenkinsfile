pipeline {
    // agent any
	// agent { docker { image 'maven:3.6.3'}}
    stages {
        stage('Build') {
            steps {
                // sh 'mvn --version'
				echo 'BRANCH NAME - $env.BRANCH_NAME'
				echo 'BUILD ID - $env.BUILD_ID'
				echo 'BUILD NUMBER - $env.BUILD_NUMBER'
				echo 'JOB NAME - $env.JOB_NAME'
				echo 'BUILD TAG - $env.BUILD_TAG'

            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Integration Test'
            }
        }
    }
	post {
        always {
            echo 'This script is run always'
        }
        success {
            echo 'This script is run when it is success'
        }
        failure {
            echo 'This script is run when it is failure'
        }
    }
}
