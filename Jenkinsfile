pipeline 
{
    agent none //jenkins_slave
    
    stages {  
        stage('Git-secrets') {
            steps {
                echo 'This script is identifying the Git secrets'  		
		//sh 'sudo trufflehog --entropy false --regex WebGoat'
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
