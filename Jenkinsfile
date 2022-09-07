pipeline{
    
    agent{
        label "node"
       
    }
    stages{
        def registryProjet = 'https://rschainlab.jfrog.io/artifactory/demorepo/'
        def IMAGE = "${registryProjet}:version-${env.BUILD_ID}"
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
                sh 'docker build("$IMAGE",  '.')'
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
