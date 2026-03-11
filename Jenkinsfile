//Declarative
pipeline {
    agent any
	//agent { docker { image 'maven:3.6.3'} }

    stages {

       
	    stage('Build') {
            steps {
                //sh 'mvn --version'
                echo 'Build' 
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_URL - $env.BUILD_URL"

            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo Test step running'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'echo Deploy step running'
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
