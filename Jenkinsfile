/*
pipeline {
    agent any
 
    environment {
        FLY_API_TOKEN=credentials('FLY_API_TOKEN')
    }
 
    tools {
        nodejs "nodejs-18"
    }
 
    triggers{
        githubPush()
    }
    
    stages {
 
        stage('Install Fly.io') {
            steps {
                echo 'Installing Fly.io...'
                withCredentials([string(credentialsId: 'FLY_API_TOKEN', variable: 'FLY_API_TOKEN')]) {
                    sh '''
                        # Instalar flyctl si no está ya disponible
                        curl -L https://fly.io/install.sh | sh
                        export FLYCTL_INSTALL="/var/jenkins_home/.fly"
                        export PATH="$FLYCTL_INSTALL/bin:$PATH"
                        # Autenticarse con Fly.io
                        fly auth token $FLY_API_TOKEN
                    '''
                }
                
            }
        }
        
        stage('Install dependencies'){
            steps {
                echo 'Installing...'
                sh 'npm install'
            }
        }
        stage('Run test'){
            steps{
                echo 'Running test'
                sh 'npm run test'
            }
        }
        stage('Pintar credencial'){
            steps{
                echo 'Hola esta es mi credencial: $FLY_API_TOKEN'
            }
        }
 
        stage('Deploy to Fly.io') {
            steps {
                echo 'Deploying the project to Fly.io...'
                sh '/var/jenkins_home/.fly/bin/flyctl deploy --app curso-devops-jenkins-bitter-wind-1309 --remote-only'
            }
        }
    }
}



pipeline {
    agent any
 
    environment {
        FLY_API_TOKEN=credentials('FLY_API_TOKEN')
    }
 
    tools {
        nodejs "nodejs-18"
    }
 
    triggers {
        githubPush() 
    }
    
    stages {
        stage('Install Fly.io') {
            steps {
                echo 'Installing Fly.io...'
                withCredentials([string(credentialsId: 'FLY_API_TOKEN', variable: 'FLY_API_TOKEN')]) { 
                    sh '''
                        # Instalar flyctl si no está ya disponible
                        curl -L https://fly.io/install.sh | sh
                        export FLYCTL_INSTALL="/var/jenkins_home/.fly"
                        export PATH="$FLYCTL_INSTALL/bin:$PATH"
                        # Autenticarse con Fly.io
                        fly auth token $FLY_API_TOKEN
                        fly version // Verifica que flyctl esté instalado y accesible
                    '''
                }
            }
        }
        
        stage('Install dependencies') {
            steps {
                echo 'Installing...'
                sh 'npm install' 
            }
        }
        
        stage('Run tests') {
            steps {
                echo 'Running tests...'
                sh 'npm run test' 
            }
        }
        
        stage('Deploy to Fly.io') {
            steps {
                echo 'Deploying the project to Fly.io...'
                sh '/var/jenkins_home/.fly/bin/flyctl deploy --app curso-devops-jenkins-bitter-wind-1309 --remote-only' 
            }
        }
    }
}

*/

pipeline {
    agent any
 
    environment {
        FLY_API_TOKEN = credentials('FLY_API_TOKEN')  // Cargar las credenciales
    }
 
    tools {
        nodejs "nodejs-18"
    }
 
    triggers {
        githubPush() 
    }
    
    stages {
        stage('Install Fly.io') {
            steps {
                echo 'Installing Fly.io...'
                script {
                    // Instalar flyctl si no está ya disponible
                    sh 'curl -L https://fly.io/install.sh | sh'
                    // Establecer el path para flyctl
                    sh 'export FLYCTL_INSTALL="/var/jenkins_home/.fly"'
                    sh 'export PATH="$FLYCTL_INSTALL/bin:$PATH"'
                    // Autenticarse con Fly.io
                    withCredentials([string(credentialsId: 'FLY_API_TOKEN', variable: 'FLY_API_TOKEN')]) { 
                        sh 'fly auth token $FLY_API_TOKEN'
                    }
                    // Verificar que flyctl esté instalado y accesible
                    sh 'fly version' 
                }
            }
        }
        
        stage('Install dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install' 
            }
        }
        
        stage('Run tests') {
            steps {
                echo 'Running tests...'
                sh 'npm run test' 
            }
        }
        
        stage('Deploy to Fly.io') {
            steps {
                echo 'Deploying the project to Fly.io...'
                sh '/var/jenkins_home/.fly/bin/flyctl deploy --app curso-devops-jenkins-bitter-wind-1309 --remote-only' 
            }
        }
    }
}
