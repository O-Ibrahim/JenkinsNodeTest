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
            mail bcc: '', body: "<b>Success</b>", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Project Worked", to: "Osama.i.adam@gmail.com";
        }
        failure{
            echo "Build failed."
            mail bcc: '', body: "<b>Fail</b>", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Project Failed", to: "Osama.i.adam@gmail.com";
        }
        always{
           echo "Cleaning up..."
           sh 'rm node_modules -rf'
           echo "Done"
        }
    }
}