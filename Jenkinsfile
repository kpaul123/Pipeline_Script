pipeline {
    agent any
    stages {
	
	    stage('Git Check-out') {
		
		    steps {
			    echo 'GIT Checkout'
		git 'https://github.com/kpaul123/Pipeline_Script.git'	
		    }
	    }
	    
	stage('Non-Parallel Stage') {
	   
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
