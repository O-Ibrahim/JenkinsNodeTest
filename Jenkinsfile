pipeline{
    agent any
    
    tools {nodejs "node"}
    
    stages {
        stage("Cloning Git"){
            steps{
                echo "Initiate Cloning"
                git "git@github.com:O-Ibrahim/JenkinsNodeTest.git"
                echo "Initiate Done"
            }
        }
        stage("Installing Dependencies"){
            steps{
                echo "Initiate Installing Dependencies"
                sh "npm install"
                echo "Installing Dependencies Done"
            }
        }
        stage("Test"){
            steps{
                echo "Running Tests"
                sh "npm test"
                echo "Running Tests Done"
            }
        }
    }
    post{
        success{
            echo "Build successful."
        }
        failure{
            echo "Build failed."
        }
        always{
           // echo "Cleaning up..."
           // sh "rm -r /var/jenkins_home/jobs/GithubTest/"
           echo "Done"
        }
    }
}