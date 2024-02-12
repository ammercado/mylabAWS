pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

         // Stage3 : Public the artefacts to nexus
         stage ('Public to Nexus'){
            steps {
               nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '48f4b7b6-44d0-4b5c-b536-7225f45da704', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.142:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'VinaysDevOpsLab-SNAPSHOT', version: '0.0.4-SNAPSHOT'

            }
        }

       // Stage3 : Deploying
        // stage ('Deploy'){
        //    steps {
          //      echo ' deploying......'

          //  }
       // }
        
        // Stage3 : Publish the source code to Sonarqube
       // stage ('Sonarqube Analysis'){
        //    steps {
         //       echo ' Source code published to Sonarqube for SCA......'
         //       withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
         //            sh 'mvn sonar:sonar'
          //      }

          //  }
       // }

        
        
    }

}