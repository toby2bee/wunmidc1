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
                echo ' testing......pom version2'

            }
        }

        // Stage3 : Deplokying
        stage ('Test'){
            steps {
                echo ' testing.......'
                
            }

            }
        }

        
        
    }

}