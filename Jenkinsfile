
pipeline {
    agent { label 'prt-task' }

    stages {
        stage('Clone Repository') {
            steps {
                git url: "https://github.com/ReemaR123/Website-PRT-ORG", branch: 'main'
            }
        }
    }
}
