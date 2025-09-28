pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                git url: 'https://github.com/PradPersonal/FaskApp.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Setting up environment and installing dependencies...'
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
                    source venv/bin/activate
                    python -m pytest test_app.py
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // NOTE: This is a placeholder. You will need to replace this
                // with actual deployment commands for your target environment.
                // For example: SSH commands, Docker deployment, or cloud provider CLI.
                sh 'echo "Deployment step would go here"'
            }
        }
    }
}
