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
        stage("Build Stage"){
            steps{
                dir("Docker/backend"){
                    
                    sh "docker build -t app-backend . "
                    
                }
                dir("Docker/frontend"){
                    
                    sh "docker build -t app-frontend . "
                    
                }
                dir("Docker"){
                    
                    sh "docker-compose up --build "
                    
                }                
            }
        }

    }
}
