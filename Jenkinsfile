pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                echo 'Installing Node.js v22'
                sh 'curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash'
                sh '. ~/.nvm/nvm.sh && nvm install 22'
            }
        }

        stage('Build') {
            steps {
                echo 'Show npm vers.'
                sh '. ~/.nvm/nvm.sh && npm -v'
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
