pipeline {
    agent any

    stages {
        stage('github config') {
            steps {
                git url:'https://github.com/sandippatil17/jen_repo.git', branch:'main'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        stage('docker container build') {
            steps {
                sh 'docker rm -f myappcontainer || true'
                sh 'docker run -d --name myappcontainer -p 80:80 myapp'
            }
        }
    }
}
