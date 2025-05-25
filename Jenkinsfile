pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials("dhubcred")
    }
    agent {
        label 'prt-task'
    }
    stages {
        stage('Git') {
            steps {
                git url:'https://github.com/ReemaR123/Website-PRT-ORG', branch:'main'
            }
        }
        stage('Docker') {
            steps {
                sh 'sudo docker login -u ${DOCKERHUB_CREDENTIALS_USR} -p ${DOCKERHUB_CREDENTIALS_PSW}'
                sh 'sudo docker build /home/ubuntu/jenkins/workspace/Testpipeline/ -t reemar123/prt-task'
                sh 'sudo docker push reemar123/prt-task'
            }
        }
    }
}
