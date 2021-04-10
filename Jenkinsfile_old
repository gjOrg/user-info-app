pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                //sh 'svn --version'
               sh 'node userapp.js'
                //sh 'nohup node start'
               sh 'sleep 1m'
                sh 'curl -v http://localhost:8089'
            }
        }
    }
}
