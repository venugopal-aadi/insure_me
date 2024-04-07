pipeline {
  agent any

  tools{
    maven 'M2_HOME'
    }
stages {
stage('Git Checkout') {
 steps {
   echo 'This is for cloning gitrepo'
   git branch: 'main', url: 'https://github.com/venugopal-aadi/insure_me.git'
                       }
}
stage('Create Package') {
 steps {
   sh 'mvn package'
 }
}
stage('Publish the HTML Reports') {
      steps {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/venu_proj/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
        
}docker 
}
 stage('Create a Docker image from the Package Insure-Me.jar file') {
      steps {
       sh 'docker build -t venu02/insure-me-proj:2.0 .'
 }
 }
  stage('Login to Dockerhub') {
      steps {

sh 'docker login -u venu02 -p Samba$002'

      }
  }
        
}
}
