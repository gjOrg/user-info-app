def dockerImage

pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
               // sh 'node --version'
                //sh 'svn --version'
             //  sh 'node userapp.js'
                //sh 'nohup node start'
              // sh 'sleep 1m'
               // sh 'curl -v http://localhost:8089'
               
               script{
                	def commit = checkout scm
                    // we set BRANCH_NAME to make when { branch } syntax work without multibranch job
                    env.BRANCH_NAME = commit.GIT_BRANCH.replace('origin/', '')

                   
                     def testImage = docker.build("test-image", ".","--build-arg v1.0")
              		 sh 'echo done'
               }
            }
        }
    }
}
