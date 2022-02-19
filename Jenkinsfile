pipeline {
    agent any
	// agent { docker { image 'maven:3.6.3'}}
	environment{
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"

	}
    stages {
        stage('Checkout') {
            steps {
                sh 'mvn --version'
                sh 'docker version'

				echo "BRANCH NAME - $env.BRANCH_NAME"
				echo "BUILD ID - $env.BUILD_ID"
				echo "BUILD NUMBER - $env.BUILD_NUMBER"
				echo "JOB NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.BUILD_TAG"

            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn failsafe:integration-test failsafe:verify'
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
