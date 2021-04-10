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

                   
                     def testImage = docker.build("test-image", ".")
                     
                      testImage.inside('-p 8089:8089 -v /tmp:/tmp') {
     				   sh 'echo test'
     				   sh 'pwd'
     				    sh 'node userapp.js'
               			 //sh 'nohup node start'
              			 sh 'sleep 1m'
                		sh 'curl -v http://localhost:8089'
     				   
  					  }
              		 sh 'echo done'
               }
            } 
        }
    }
}
