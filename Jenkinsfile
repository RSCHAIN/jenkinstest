node {  
    def registryProjet = 'https://rschainlab.jfrog.io/artifactory/demorepo/'
    def IMAGE = "${registryProjet}:version-${env.BUILD_ID}"

 
    stage ('Clone') {
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
        docker.withRegistry('https://rschainlab.jfrog.io','demorepo'){ 
              img.push ()
              img.push()
        }   
    }   
}
