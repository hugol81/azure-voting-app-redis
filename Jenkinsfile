pipeline {
    agent any
    
    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
                echo "$WORKSPACE"
            }
        }
        stage('Docker Build') {
            steps {
                sh 'cd azure-vote/'
                echo "$WORKSPACE"
                sh '''sudo docker images -a
                sudo docker build -t jenkins-pipeline .
                sudo docker images -a
                cd ..'''
                echo "$GIT_BRANCH"
            }
        }
    }
}