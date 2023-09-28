pipeline {
    agent {
        docker {
            // Use a Maven Docker image as the build environment
            image 'maven:3.8.4' // Replace with the desired Maven version
            args '-v $HOME/.m2:/root/.m2' // Mount the local Maven repository for caching
        }
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from your version control system (e.g., Git) into a workspace
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Build your Maven project
                sh 'mvn clean install'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests or other post-build steps here
            }
        }
        
        stage('Deploy') {
            steps {
                // You can add deployment steps here as needed
            }
        }
    }
    
    post {
        success {
            // Actions to take if the build succeeds
            echo 'Build successful!'
        }
        failure {
            // Actions to take if the build fails
            echo 'Build failed!'
        }
    }
}
