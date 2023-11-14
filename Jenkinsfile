pipeline {
    agent any

    environment {
        // Set the PATH to include the default location for npm
        // Replace with the actual location if npm is installed elsewhere
        PATH = "$PATH:/usr/local/bin"
    }
    
    stages {
        stage('Prepare Environment') {
            steps {
                // Source nvm and install if not already available.
                sh 'if [ -s "$HOME/.nvm/nvm.sh" ]; then . "$HOME/.nvm/nvm.sh"; fi'
                sh 'if [ -s "$HOME/.nvm/bash_completion" ]; then . "$HOME/.nvm/bash_completion"; fi'
                // Install the version of Node.js you want to use
                sh 'nvm install 16'
                // Use the installed version
                sh 'nvm use 16'
            }
        }
        stage('Build') { 
            steps {
                // Now npm should be available, and the right Node.js version should be in use.
                sh 'npm install' 
            }
        }
    }
}
