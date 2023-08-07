pipeline {
    
  agent any
        
        stage('RUN TEST') {
            
            agent {
             label "docker-agent-python"
          }
          
            steps {
                sh '''
                python3 --version
                pip3 install pytest
                pytest -v
           
                '''
            }
        }
        
        stage('BUILD') {
            steps {
                echo 'Building Docker Image'
            }
        }
        
        stage('DEPLOY') {
            steps {
                echo 'Deploying'
            }
        }
    }
}
