pipeline {
    agent any

    stages {
        stage('git configure') {
            steps {
                git url:'https://github.com/sandippatil17/jen_repo.git',
                branch:'main'
            }
        }
        stage('docker image bulid') {
            steps {
                sh 'docker build -t myapp.'
            }
        }
        stage('docker container run') {
            steps {
                sh 'docker rm -f myappcontainer || true'
                sh 'docker run -d --name myappcontainer -p 8080:myapp'
            }
        }
    }
}
