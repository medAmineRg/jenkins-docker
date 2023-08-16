pipeline {
    agent {
        docker {
            image 'node:18.17.1-alpine3.18' 
        }
    }
    stages {
        stage('Build docker image'){
            steps{
                sh 'docker build -t mohamed99amine/devkhobzix .'
            }
        }

    stage('Push') {
        steps {
            withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub')]) {
                sh 'docker login -u mohamed99amine -p ${dockerhub}'
            }
            sh 'docker push mohamed99amine/devkhobzix'

        }
    }
    }
}
