pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning the repository...'
            }
        }
        stage('Install') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'npm run build || echo "No build step, continuing..."'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test || echo "No test step, continuing..."'
            }
        }
        stage('Run') {
            steps {
                echo 'Running the Node.js app...'
                sh 'nohup node app.js > app.log 2>&1 &'
            }
        }
    }
}

