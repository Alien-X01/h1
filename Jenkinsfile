pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''#!/bin/bash
                    docker stop $(docker ps -aq)
                    docker rm $(docker ps -aq)
                    docker rmi $(docker images)
                    docker build -t pluto .
                    docker run --name pra -d -p 8082:80 pluto'''
            }
        }
    }
}
