pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials("dhubcred")
    }
    agent {
        label 'K-M'
    }
    stages {
        stage('Git') {
            steps {
                git url:'https://github.com/ReemaR123/Website-PRT-ORG/tree/patch-2', branch:'patch-2'
            }
        }
        stage('Docker') {
            steps {
                sh 'sudo docker login -u ${DOCKERHUB_CREDENTIALS_USR} -p ${DOCKERHUB_CREDENTIALS_PSW}'
                sh 'sudo docker build /home/ubuntu/jenkins/workspace/Test-PRT-Pipeline/ -t reemar123/prt-task'
                sh 'sudo docker push reemar123/prt-task'
            }
        }
        stage('Kubernetes') {
            steps {
                sh 'kubectl apply -f deploy.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
