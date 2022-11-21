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
	   agent node
    parallel {
    stage ('STAGE2') {
      steps {
        echo "This is stage 2" 
        sh 'sleep 5; exit 0'
      }  
    }  
    
    stage ('STAGE3') {
      steps {
        echo "This is stage3" 
        sh 'sleep 5; exit 0'
	      }
      }
    }
  }

    stage ('STAGE4') {
      steps {
        echo "This is stage4" 
        sh 'sleep 5'
	      }
      }  
    }  
  } 
