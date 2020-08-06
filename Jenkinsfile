pipeline 
{
    agent any
    options 
	{
        skipDefaultCheckout(true)  // To Avoid Default Checkout 
    	}
    stages {
        stage('Checkout') {
            steps {
                //sh 'dir'
		echo 'This script is cloning the repo.'  
                //sh 'rm -rf pivaadescsec'
                //sh 'git clone https://github.com/parag85/pivaadescsec.git'
                //sh 'cd pivaadescsec/'
                //sh 'ls'
                //sh 'whoami'
            }
        }
            
        stage('Git-secrets') {
            steps {
                echo 'This script is identifying the Git secrets'  		
		//sh 'sudo trufflehog --entropy false --regex pivaadescsec'
                }
            }
	  
        stage('OAST') {
            steps {
              echo 'This script is identifying the OAST vulnerabilities'
            }
        }
        
        stage('SAST') {
            steps {
              echo 'This script is identifying the SAST vulnerabilities'
            }
        }
        
        stage('DAST') {
            steps {
                echo 'This script is identifying the DAST vulnerabilities'
            }
        }
    }
}
