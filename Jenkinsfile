pipeline {
    
  agent {
             label "docker-agent-python"
          }
    
    stages {
        
        stage('CHECK OUT') {
            steps {
                
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/aafetorgbor/test.git']]])
            }
        }
        
        stage('RUN TEST') {
          
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
