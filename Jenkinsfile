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
		sh 'rm trufflehog || true'
		sh 'docker pull gesellix/trufflehog'
		//sh 'docker run -t gesellix/trufflehog --json https://github.com/testappkgs/vulnado.git > trufflehog'
		//sh 'cat trufflehog'
                }
            }
	  
        stage('SCA') {
            steps {
              echo 'This script is identifying the OAST vulnerabilities'
	      sh 'rm owasp* || true'
              sh 'wget "https://raw.githubusercontent.com/parag85/AppSecPipeline/master/owasp-dependency-check.sh"'
              sh 'chmod +x owasp-dependency-check.sh'
              sh 'bash owasp-dependency-check.sh'
	      sh 'cat /var/lib/jenkins/workspace/DevSecOps_Pipeline/reports/dependency-check-report.xml'
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
