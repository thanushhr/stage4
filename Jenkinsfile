pipeline {
  agent any	
  stages {

    stage ('STAGE1') {
      steps {
        echo "This is stage1" 
        sh ''' 
		      echo "Hello"
	        exit 0 
	        '''
      }  
    } 
   stage ('PARALLEL STAGES 2 & 3') {
    parallel {
    stage ('STAGE2') {
	    agent {label 'node1'}
      steps {
        echo "This is stage 2" 
	echo "$BUILD_NUMBER"
        sh 'sleep 5; exit 0'
      }  
    }  
    
    stage ('STAGE3') {
	    agent {label 'node1'}
      steps {
        echo "This is stage3" 
	echo "$BUILD_NUMBER"
        sh 'sleep 5; exit 0'
	      }
      }
    }
  }

    stage ('STAGE4') {
      agent any
      steps {
        echo "This is stage4" 
        sh 'sleep 5'
	      }
      }  
    }  
  } 
