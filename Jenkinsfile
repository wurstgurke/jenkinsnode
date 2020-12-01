pipeline{
    agent any
    stages{
        stage('Build image') {
            /* This builds the actual image; synonymous to
            * docker build on the command line */
            steps{
                sh "pwd"
                sh "ls -la"
                sh "docker build -t localhost:8083/wurstgurke/jenkinsnode:latest ."
                sh "docker login -u admin -p ncc1701 localhost:8083"
                sh "docker push localhost:8083/wurstgurke/jenkinsnode:latest"
            }
        }
    }
}
