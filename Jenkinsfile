pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    echo "Workspace:"
                    pwd

                    echo "Node Version:"
                    node --version

                    echo "NPM Version:"
                    npm --version

                    echo "Installing Dependencies"
                    npm ci

                    echo "Building Application"
                    npm run build
                '''
            }
        }
    }
}