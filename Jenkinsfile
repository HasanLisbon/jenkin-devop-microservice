pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build'
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
