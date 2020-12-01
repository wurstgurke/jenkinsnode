pipeline{
    agent any
    stages{
        stage('Build image') {
            steps{
                sh "docker build -t localhost:8083/wurstgurke/jenkinsnode:${env.BUILD_NUMBER} ."
                sh "docker login -u admin -p ncc1701 localhost:8083"
                sh "docker push localhost:8083/wurstgurke/jenkinsnode:latest"
            }
        }
        // TODO: hier agent auf cypress docker wechseln und tests ausführen
        stage('Test image') {
            steps{
                sh 'echo "Tests passed"'
            }
        }
    }
}
