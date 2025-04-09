node {
    stage('Download code from git repository') {
    git branch: 'test', url: 'https://github.com/clouddevopseng/2pmproj.git'
             }
   stage('Convert into Artifacts') {
   sh 'mvn package'
           }
  stage('Deployment'){
  deploy adapters: [tomcat9(credentialsId: 'd08087e1-dc79-4248-8079-f4b146c50a27', path: '', url: 'http://172.31.14.42:8080')], contextPath: '/test', war: '**/*.war'
  }
}
