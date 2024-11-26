pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Shivani554/commitid.git'
            }
        }
        stage('Fetch Commit IDs') {
            steps {
                script {
                    def commitIds = sh(
                        script: "git log -n 2 --pretty=format:'%H'",
                        returnStdout: true
                    ).trim().split("\n")
                    echo "Latest Commit ID: ${commitIds[0]}"
                    echo "Second Latest Commit ID: ${commitIds[1]}"
                }
            }
        }
    }
}
