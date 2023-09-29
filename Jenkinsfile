pipeline {
 agent any
 environment{
        SNAP_REPO = 'vprofile-snapshot'
		NEXUS_USER = 'admin'
		NEXUS_PASS = 'admin123'
		RELEASE_REPO = 'vprofile-release'
		CENTRAL_REPO = 'vpro-maven-central'
		NEXUSIP = '10.0.1.133'
		NEXUSPORT = '8081'
		NEXUS_GRP_REPO = 'vpro-maven-group'
      NEXUS_LOGIN = 'nexuslogin'
      SONARSERVER = 'mysonar'
      SONARSCANNER = 'sonarscanner'
 }
 stages{
   stage('git chekcout'){
      steps{
        git branch: 'master' , url: 'https://github.com/vscbobba/vprofile-cicd.git'
      }
   }
   stage('build') {
      steps{
         sh 'mvn -s settings.xml -DskipTests install'
      }   
      post{
            success{
                echo "archive artifacts"
                archiveArtifacts artifacts: '**/*.war'
            }
      } 
    }
 }
}  
