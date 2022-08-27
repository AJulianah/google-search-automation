pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/playwright:v1.17.2-focal'
        }
    }
    stages {
        stage('Install playwright'){
            steps {
                sh '''
                    npm i -D @playwright/test
                    npx playwright install
                '''
            }
        }
        stage('test'){
            steps {
                sh '''
                    npx test --list
                    npx playwright test
                '''
            }
        }
    }
}
