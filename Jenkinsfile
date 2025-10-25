pipeline{
	agent any
	
	stages{
		
		stage('Checkout'){
			steps{
				git branch: 'master', url: https://github.com/KumaresanGanesh/git-learning.git
			}
		}
		
		stage('Build'){
			steps{
				sh'mvn clean compile'
			}
		}
		
		stage('Run'){
			steps{
				sh 'java -cp target/classes myProject.jenkins.App'
			}
			
			}
		}
		
	post{
		always{
			junit 'target/surefire-reports/*.xml'
		}
		success{
			echo 'Build and test Successfull'
		}
		failure{
			echo 'Build or Test Failed'
		}
	}	
}