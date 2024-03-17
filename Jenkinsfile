pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM 'H/5 * * * *'
    }
    stages {
        stage('Environment') {
            steps {
                echo "Environment.."
                sh '''
                python3 -m venv .venv
                source .venv/bin/activate
                cd myapp
                python3 -m pip install -r requirements.txt
                '''
            }
        }
       stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
} 