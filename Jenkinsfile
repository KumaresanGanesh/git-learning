pipeline{
	agent any
	
	stages{	
		stage('Checkout'){
			steps{
				git branch: 'master', url: 'https://github.com/KumaresanGanesh/git-learning.git'
			}
		}
		
		stage('Build & Test'){
			steps{
				bat'mvn clean test'
			}
		}
		
		stage('Run'){
			steps{
				bat'java -cp target/classes myProject.Jenkins.App'
			}
			
			}
		}
		
	post{
		success{
			echo 'Build and test Successfull'
		}
		failure{
			echo 'Build or Test Failed'
		}
	}	
}