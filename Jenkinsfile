node {
    stage('Checkout') {
        checkout scm
    }

    stage('Install Dependencies') {
        docker.image('node:20').inside {
            sh 'npm install'
        }
    }

    stage('Build') {
        docker.image('node:20').inside {
            sh 'npm run build'
        }
    }

    stage('Test') {
        docker.image('node:20').inside {
            sh 'npm test -- --watchAll=false'
        }
    }
}
