pipeline {
    agent any

    environment {
        NVM_DIR = "$HOME/.nvm"
    }

    stages {
        stage('Prepare') {
            steps {
                echo 'Installing Node.js v22'
                sh 'curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash'
                sh 'export NVM_DIR="$HOME/.nvm" && [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" && nvm install 22'
            }
        }

        stage('Build') {
            steps {
                echo 'Show npm version'
                sh 'export NVM_DIR="$HOME/.nvm" && [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" && npm -v'
            }
        }

        stage('Test') {
            steps {
                echo 'Displaying Jenkins environment variable'
                sh 'echo "JENKINS_URL=$JENKINS_URL"'
            }
        }
    }
}
