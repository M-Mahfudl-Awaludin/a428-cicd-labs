node {
    stage('Checkout') {
        git branch: 'react-app',
            url: 'https://github.com/M-Mahfudl-Awaludin/a428-cicd-labs.git'
    }

    stage('Install Dependencies') {
        dir('react-app') {
            sh 'npm install'
        }
    }

    stage('Build') {
        dir('react-app') {
            sh 'npm run build'
        }
    }

    stage('Deploy') {
        dir('react-app') {
            sh '''
            npm install -g serve
            serve -s build -l 3000 &
            '''
        }
    }
}
