pipeline {
 agent any

 stages{
   stage('git chekcout'){
      steps{
        git branch: 'master' , url: 'https://github.com/vscbobba/vprofile-cicd.git'
      }
   }
   stage('build') {
      steps{
         sh 'mvn install'
      }
   }
 }
}  
