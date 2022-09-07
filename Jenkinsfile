pipeline{
    
    agent any
    stages{
       
        stage("clone"){
            
            steps{
                echo "========executing clone========"
                sh 'checkout scm'
            }
            post{
                always{
                    echo "========top========"
                }
                success{
                    echo "======== wahou lomb12========"
                }
                failure{
                    echo "======== run again========"
                }
            }
        }
         stage("build"){
            
            steps{
                echo "========executing clone========"
                sh 'docker build .'
            }
            post{
                always{
                    echo "========top========"
                }
                success{
                    echo "======== wahou lomb12========"
                }
                failure{
                    echo "======== run again========"
                }
            }
        }
    }
   
}
