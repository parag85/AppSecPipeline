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
                echo 'This script is cloning the repo.'  
                sh 'rm -rf WebGoat'
                sh 'git clone https://github.com/parag85/WebGoat.git'
                //sh 'cd WebGoat/'
                //sh 'ls'
                sh 'whoami'
            }
        }
            
        stage('Git-secrets') {
            steps {
                echo 'This script is identifying the Git secrets'  
		sh 'sudo trufflehog --entropy false --regex WebGoat'
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
