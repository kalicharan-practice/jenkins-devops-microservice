//Declarative
pipeline {
    agent any
	//agent { docker { image 'maven:3.6.3'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}

    stages {

       
	    stage('Checkout') {
            steps {
                sh 'mvn --version'
				sh 'docker --version'
                echo 'Build' 
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_URL - $env.BUILD_URL"

            }
        }

		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}

        stage('Test') {
            steps {
                //echo 'Running tests...'
                //sh 'echo Test step running'
				sh 'mvn Test'
            }
        }

        stage('Integration Test') {
            steps {
                //echo 'Deploying application...'
                //sh 'echo Deploy step running'
				sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }

        success {
            echo 'Build successful!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
