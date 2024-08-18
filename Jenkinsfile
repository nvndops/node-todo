pipeline {
    agent { label "dev"}
    
    stages {
        
        stage("Code"){
            steps{
                git url: "https://github.com/nvndops/node-todo.git", branch: "main"
            }
        }
        stage("Build and Test"){
            steps{
                sh "docker build -t node-app-test-new ."
            }
        }
        stage("Deploy"){
            steps{
                sh "docker compose down && docker compose up -d"
            }
        }
    }
}
