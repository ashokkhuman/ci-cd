pipeline { 
    environment { 
        registry = "ashokdocker123/python-flask" 
        registryCredential = 'ashokDockerCredential' 
        dockerImage = '' 
    }
    agent any 
    stages { 
        stage('Cloning our Git') { 
            steps { 
                git branch:'main', url: 'https://github.com/ashokkhuman/ci-cd.git' 
            }
        } 
        stage('Spin up infra using terraform') {
            steps {
                sh '''
                    pwd
                    cd terraformdockerinfra
                    terraform init
                    terraform apply -auto-approve
                '''
            }
        }
    }
    
}