node {
  stage('Download code from git repository') {
  git branch: 'dev', url: 'https://github.com/clouddevopseng/2pmproj.git'
  }
  stage('Convert into Artifacts') {
  sh 'mvn package'
  }
  stage('Deployment'){
  deploy adapters: [tomcat9(credentialsId: '880f6844-b42f-4dc2-a41f-157d6118917e', path: '', url: 'http://172.31.13.238:8080')], contextPath: '/dev', war: '**/*.war' 
  }
}
