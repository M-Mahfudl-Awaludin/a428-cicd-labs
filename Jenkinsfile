node {

    def nodeHome = tool name: 'node18', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"

    stage('Checkout') {
        checkout scm
    }

    stage('Install Dependencies') {
        sh 'npm install'
    }

    stage('Build') {
        sh 'npm run build'
    }

    stage('Test') {
        sh 'npm test -- --watchAll=false'
    }
}
