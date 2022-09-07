node {
 def registryProjet = ''
 def IMAGE = ""
 
 stage ('clone') {
        checkout scm 
        }
        
 def img = stage('build') {
        docker.build("$IMAGE",  '.')
        }
        
 stage ('Run') {
         img.withRun("--name run-$BUILD_ID -p 80:80") { c -> 
         sh 'curl localhost'
         }
      }
      
  stage('Push') { 
         docker.withRegistry('','') {
              img.push 'latest'
              img.push()
              }
              
           }
           
       }
