pipeline {
    agent none
    stages {
	
	    stage('Git Check-out') {
		agent {
                        label "master"
		}
		    steps {
			    echo 'GIT Checkout'
		git 'https://github.com/kpaul123/Pipeline_Script.git'	
		    }
	    }
	    
	stage('Non-Parallel Stage') {
	    agent {
                        label "master"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "master"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
