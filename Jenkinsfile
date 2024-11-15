pipeline {
    agent any
	
    enviroment {
    COMPOSE_FILE = 'docker-compose.yml'
    } 
    stages {
        stage('Build') { 
            steps {
                script {
		sh '''
		docker stop $(docker ps -aq) && docker rm $(docker ps -aq)
		docker compose down 
		docker compose up --build -d  	
	        '''  
		}
            }
        }
    }
}
