//Declarative
pipeline {
    //agent any
	agent { docker { image 'maven:3.6.3'} }

    stages {

       
	    stage('Build') {
            steps {
                sh 'mvn --version'
                echo 'Build' 
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
