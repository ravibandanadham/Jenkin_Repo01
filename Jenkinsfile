pipeline {
    agent any
     tools {
        // Install the Maven version configured as "M3" and add it to the path.
       maven "Maven-3.9.5"
    }
    stages {
        stage (git_clone) {
            steps {
              git credentialsId: 'Ravikumar', url: 'https://github.com/ravibandanadham/Jenkin_Repo01.git'
            }
        }
        stage (Compile_packge){
            steps{
            sh 'mvn clean compile'
            }
        }
        stage (Test_packge){
            steps{
                sh 'mvn test'
            }
        }
        stage(Build_war_file){
            steps{
                sh 'mvn package'
            }
        }
        stage(nexus_push_warfile){
            steps{
                sh 'mvn deploy'
            }
        }
        }
    }

