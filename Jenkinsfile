pipeline {
    agent { label "dev"}
    
    stages {
        
        stage("code"){
            steps{
                git url: "https://github.com/nvndops/node-todo.git", branch: "main"
            }
        }
        stage("build and test"){
            steps{
                sh "docker build -t node-app-test-new ."
            }
        }
        stage("deploy"){
            steps{
                sh "docker compose down && docker compose up -d"
            }
        }
    }
}
