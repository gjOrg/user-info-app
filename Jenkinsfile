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
               
               
              // docker.image('mysql:5').withRun('-e "MYSQL_ROOT_PASSWORD=my-secret-pw" -p 3306:3306') { c ->
        /* Wait until mysql service is up */
    //    sh 'while ! mysqladmin ping -h0.0.0.0 --silent; do sleep 1; done'
     //   /* Run some tests which require MySQL */
     //   sh 'make check'
   // }
               script{
                	def commit = checkout scm
                    // we set BRANCH_NAME to make when { branch } syntax work without multibranch job
                    env.BRANCH_NAME = commit.GIT_BRANCH.replace('origin/', '')

                   
                     def testImage = docker.build("test-image", ".")

                     docker.image("test-image").withRun('-p 8089:8089 -v /tmp:/tmp') { c ->
        /* Wait until mysql service is up */
      //  sh 'while ! mysqladmin ping -h0.0.0.0 --silent; do sleep 1; done'
        /* Run some tests which require MySQL */
         sh 'sleep 1m'
        sh 'echo ganesh'
    }


                     // testImage.inside('-p 8089:8089 -v /tmp:/tmp') {
     				  // sh 'echo test'
     				   //sh 'pwd'
     				   //sh 'ls -l'
     				    //sh 'npm install'
     				    //sh 'nohup node userapp.js &'
               			 //sh 'nohup node start'
              			 //sh 'sleep 1m'
                		//sh 'curl -v http://localhost:8089'
     				   
  					  //}
              		 sh 'echo done'
               }
            } 
        }
    }
}
