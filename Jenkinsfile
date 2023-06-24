pipeline {
 agent none
environment {
NAME='basava'
}
 stages { 
   stage ('BUILD') {
    agent { label 'jenkins'}
     steps {
       echo "$NAME"
      sh 'sleep 5'
	   echo $NAME
     }
   }
 stage ('TEST PARELLEL') {
  parallel {
  stage ('TEST ON CHROME') {
   agent { label 'jenkins'}
   steps {
    echo "this is test on chrome browser"
      sh 'sleep 5'
     }
   }
  stage ('TEST ON SAFARI') {
   agent { label 'jenkins'}
   steps {
    echo "this is test on safari browser"
      sh 'sleep 5'
     }
   }
  }
 }
  stage ('DEPLOY') {
   parallel {
    stage ('DEPLOY ON SERVER 1') {
   agent { label 'jenkins'}
 steps {
  echo " this is server1 deploy "
  sh 'sleep 5'
 }
  }
      stage ('DEPLOY ON SERVER 2') {
   agent { label 'jenkins'}
 steps {
  echo " this is server2 deploy "
  sh 'sleep 5'
 }
}
 }
}
 }
}

