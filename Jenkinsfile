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

                    dockerImage = docker.build("myImage:${env.BUILD_ID}",
                        "--label \"GIT_COMMIT=${env.GIT_COMMIT}\""
                        + " --build-arg MY_ARG=myArg"
                        + " ."
                    )
               sh 'echo done'
               }
            }
        }
    }
}
