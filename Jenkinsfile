
pipeline {
   agent {
        label "master"
    }
   tools {
     maven 'maven'
   }
   environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "https"
        NEXUS_URL = "nexus-lab.pp.ua"
        NEXUS_REPOSITORY = "maven-lab"
        NEXUS_CREDENTIAL_ID = "nexus-user-credentials"
    }
   stages {
     stage("Clone code from VCS") {
            steps {
                script {
                    git 'https://github.com/atrofymchuk/spring-petclinic.git';
                    
                }
            }
        }
     stage('Build') {
       steps {
         sh 'mvn clean deploy'
       }   
     }
   }
}
