pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'svn --version'
                sh 'nohup node userapp.js  --env=dev &'
                sh 'sleep 2m'
            }
        }
    }
}
