pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
    environment{
       ArtifactId = readMavenPom().getArtifactId()
       Version = readMavenPom().getVersion()
       Name = readMavenPom().getName()
       GroupId = readMavenPom().getGroupId()
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

        // Stage3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                script {

                def NexusRepo = Version.endsWith("SNAPSHOT") ? "WunmiDevOpsLab-SNAPSHOT" : "WunmiDevOpsLab-RELEASE"

                nexusArtifactUploader artifacts: 
                [[artifactId: "${ArtifactId}", 
                classifier: '', 
                file: "target/${ArtifactId}-${Version}.war", 
                type: 'war']], 
                credentialsId: 'f694a714-b8ff-47d0-b19c-b8487b929589', 
                groupId: "${GroupId}", 
                nexusUrl: '54.161.4.16:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http',
                repository: "${NexusRepo}", 
                version: "${Version}"
             }
            }
        }

        // Stage5 : Deploying
        stage ('Deploy'){
            steps {
                echo ' testing.......'
                
            }

        }
    }

        
        
}