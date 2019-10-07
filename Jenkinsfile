pipeline{
    agent any
    
    tools {nodejs "node"}
    
    stages {
        stage("Cloning Git"){
            steps{
                git "https://github.com/O-Ibrahim/JenkinsNodeTest"
            }
        }
        stage("Installing Dependencies"){
            steps{
                sh "npm install"
            }
        }
        stage("Test"){
            steps{
                sh "npm test"
            }
        }
    }
}