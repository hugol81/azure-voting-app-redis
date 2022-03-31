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
                echo 'The workspace is: "$WORKSPACE"'
                sh '''docker images -a
                docker build -t jenkins-pipeline .
                docker images -a
                cd ..'''
                echo "$GIT_BRANCH"
            }
        }
    }
}