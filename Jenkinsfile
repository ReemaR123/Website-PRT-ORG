
pipeline {
    agent { label 'prt-task' }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/example-org/sample-repo.git', branch: 'main'
            }
        }
    }
}
