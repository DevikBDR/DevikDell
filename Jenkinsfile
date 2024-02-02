pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                script {
                    git branch: 'main', url: 'https://github.com/your-repo.git'
                }
            }
        }

        stage('Build') {
            steps {
                // Your build steps go here
                script {
                    echo 'Building the code...'
                }
            }
        }

        stage('Test') {
            steps {
                // Your test steps go here
                script {
                    echo 'Running tests...'
                }
            }
        }

        stage('Deploy') {
            when {
                // Deploy only if the branch is 'main'
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                // Your deployment steps go here
                script {
                    echo 'Deploying the application...'
                }
            }
        }
    }

    post {
        success {
            // This block runs if the pipeline is successful
            echo 'Pipeline executed successfully!'
        }
        failure {
            // This block runs if the pipeline fails
            echo 'Pipeline execution failed!'
        }
    }
}
