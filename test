pipeline{
    
    agent any
    stages{
       
        stage("clone"){
            
            steps{
                echo "========executing clone========"
                sh 'checkout scm'
            }
         
        }
         stage("build"){
            
            steps{
                echo "========executing clone========"
                sh 'docker build -t my-docker-image .'
            }
        
        }
    }
   
}
