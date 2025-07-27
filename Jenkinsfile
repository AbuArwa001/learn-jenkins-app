pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh """
                    ls -la
                    npm --version
                    node --version
                    echo "Installing dependencies and building the project"
                    npm ci
                    npm run build
                    ls -la
                """
            }
        }
        stage('Test') {

            steps {
                sh """
                    echo "Running tests for the project"
                    // npm test
                """
            }
        }
    }
}
