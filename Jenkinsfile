//Declarative
pipeline {
    agent any

    stages {

       
	    stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'echo Build step running'
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
