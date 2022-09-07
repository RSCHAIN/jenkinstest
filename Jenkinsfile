node {
 def registryProjet = 'https://rschainlab.jfrog.io/artifactory/demorepo/'
 def IMAGE = "${registryProjet}:version-${env.BUILD_ID}"
 
 stage ('clone') {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/RSCHAIN/jenkinstest.git']]])
        }
        
 stage('build') {
        sh 'docker build("$IMAGE",  '.')'
        }
        
 stage ('Run') {
         sh 'docker.withRun("--name run-$BUILD_ID -p 80:80") { c -> '
         sh 'curl localhost'
         }
      }
      
  stage('Push') { 
         docker.withRegistry('https://rschainlab.jfrog.io','demorepo') {
              docker.push 'latest'
              docker.push()
              }
              
        }   

