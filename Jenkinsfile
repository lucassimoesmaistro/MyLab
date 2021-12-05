pipeline{
    //Directives
    agent any
    tools {
        maven 'Maven'
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
        
        // Stage3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                 nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '2b39a0bb-7b49-4999-a3a5-e2719087595b', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.174', nexusVersion: 'nexus3', protocol: 'http', repository: 'DevopsLab-SnapShot', version: '0.0.4-SNAPSHOT'
            }
        }

        // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo 'Deploying......'
            }
        }

    }
}