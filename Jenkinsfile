pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''#!/bin/bash
			docker stop $(docker ps -aq)
			docker rm $(docker ps -aq)
			docker rmi $(docker images)
			docker build -t mars .
			docker login -u alienx01 -p Shaddy@1996	
			docker tag mars alienx01/mars
			docker push alienx01/mars
			su jenkins
			read -s -p j
			cd
			cd workspace
			./deb.sh'''
            }
        }
    }
}
