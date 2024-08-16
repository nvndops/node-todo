pipeline {
    agent { label "dev"}
    
    stages {
        
        stage("code"){
            steps{
                git url: "https://github.com/nvndops/node-todo.git", branch: "main"
                echo 'bhaiyya code clone ho gaya'
            }
        }
        stage("build and test"){
            steps{
                sh "docker build -t node-app-test-new ."
                echo 'code build bhi ho gaya'
            }
        }
        stage("scan image"){
            steps{
                echo 'image scanning ho gayi'
            }
        }
        stage("deploy"){
            steps{
                sh "docker compose down && docker compose up -d"
                echo 'deployment ho gayi'
            }
        }
    }
}
