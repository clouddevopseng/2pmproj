node {
    stage('Download code from git repository') {
    git branch: 'qa', url: 'https://github.com/clouddevopseng/2pmproj.git'
             }
   stage('Convert into Artifacts') {
   sh 'mvn package'
           }
  stage('Deployment'){
  deploy adapters: [tomcat9(credentialsId: '00594ec5-5b5d-4859-88a1-217474cc221c', path: '', url: 'http://172.31.2.83:8080')], contextPath: '/qa', war: '**/*.war'
  }
}
