node {
    checkout scm
    stage('Preparation') {
        git 'https://github.com/jekstrom/react-demo.git/'
    }
    stage('Build') {
        sh 'npm install'
        sh 'npm run build'
    }
    withEnv(["CI=True"]) {
        sh 'npm run test'
    }
    stage('Archive') {
        archiveArtifacts artifacts: '**/build/*', fingerprint: true
    }
}