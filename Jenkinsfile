pipeline {
    agent any
    environment {
        REGISTRY = credentials('cs-git')
    }
    stages {
        stage('Build') {
            steps {
                sh('''docker login gitlab.infra.computerstein.net:4567 -u $REGISTRY_USR -p $REGISTRY_PSW ;
                docker build -t gitlab.infra.computerstein.net:4567/interns/jenkins:latest . ;
                docker push gitlab.infra.computerstein.net:4567/interns/jenkins:latest''')
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....!!!'
            }
        }
    }
}