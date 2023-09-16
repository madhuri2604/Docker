pipeline{
    agent any
    stages{
        stage("Clean Up"){
            steps {
                deleteDir()
            }
        }
        stage("clone repo"){
            steps {
                sh "git clone https://github.com/madhuri2604/Docker.git"
            }
        }
        stage("Build"){
            steps{
                dir("Docker/backend"){
                    
                    sh "sudo docker build -t app-backend . "
                    
                }
                dir("Docker/frontend"){
                    
                    sh "sudo docker build -t app-frontend . "
                    
                }
                dir("Docker"){
                    
                    sh "sudo docker-compose up  "
                    sh "sudo systemctl restart nginx"
                }                
            }
        }

    }
}
