pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from version control (e.g., GitHub)
                // Make sure you have configured the necessary credentials
                git 'https://github.com/Dewank7852/next-js.js.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js and npm if not already installed
                // For example, using Node Version Manager (nvm)
                sh 'nvm install'
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Next.js application
                sh 'npm run build'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests for your Next.js application
                sh 'npm run test'
            }
        }
        
        stage('Deployment') {
            steps {
                // Deploy your Next.js application to the server
                // This could be deploying to a hosting service or your own server
                // For example, copying the build output to the server
                sh 'rsync -avz --delete ./out/ user@your_server:/path/to/destination'
            }
        }
    }
}
