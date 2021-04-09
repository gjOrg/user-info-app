pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'svn --version'
               // sh 'nohup node userapp.js  --env=dev &'
                sh 'uid=A795252 nohup npm start &'
                sh 'sleep 1m'
                sh 'curl -v http://localhost:8089'
            }
        }
    }
}
