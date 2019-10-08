pipeline{
    agent any
    
    tools {nodejs "node"}
    
    stages {
        stage("Cloning Git"){
            steps{
                echo "Initiate Cloning"
                git "https://github.com/O-Ibrahim/JenkinsNodeTest"
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
            mail bcc: '', body: "<b>Success</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "Osama.i.adam@gmail.com";
        }
        failure{
            echo "Build failed."
            mail bcc: '', body: "<b>Fail</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "Osama.i.adam@gmail.com";
        }
        always{
           echo "Cleaning up..."
           sh 'rm node_modules -rf'
           echo "Done"
        }
    }
}