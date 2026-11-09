
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
                    echo "===== Node.js Version ====="
                    node --version

                    echo "===== NPM Version ====="
                    npm --version

                    echo "===== Project Files ====="
                    ls -la

                    echo "===== Install Dependencies ====="
                    npm ci

                    echo "===== Build Project ====="
                    npm run build

                    echo "===== Build Completed ====="
                    ls -la
                '''
            }
        }
    }
}
