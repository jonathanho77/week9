pipeline {
    agent any
	triggers {
          pollSCM('* * * * *')
     }	
    stages {
        stage('First Stage') {
            steps {
		    git url: 'https://github.com/leszko/calculator.git'
            }
            
        }
        stage('Second Stage'){
            steps {
                sh 'test $(curl calculator-service:8080/sum?a=3\\&b=4) -eq 7'
                sh 'test $(curl calculator-service:8080/div?a=3\\&b=3) -eq 1'
                
            }
            
        }
        
    }
}
