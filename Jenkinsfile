pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the sample application...'
                sh 'test -f index.html'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the sample application...'
                sh 'grep -q "Hello from DevOps CI/CD!" index.html'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh '''
                    mkdir -p "$WORKSPACE/deployed"
                    cp index.html "$WORKSPACE/deployed/index.html"
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD pipeline failed.'
        }
    }
}
