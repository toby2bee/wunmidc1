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
                echo ' testing.......................'

            }
        }

        // Stage3 : Publish the artifact to Nexus
        stage('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.5-SNAPSHOT.war', type: 'war']], credentialsId: 'f694a714-b8ff-47d0-b19c-b8487b929589', groupId: 'com.vinaysdevopslab', nexusUrl: '54.161.4.16:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'WunmiDevOpsLab-SNAPSHOT', version: '0.0.5-SNAPSHOT'
            }
        }

        // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo ' testing.......'
                
            }

        }
    }

        
        
}