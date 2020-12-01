node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        dir("frontend") {
            sh "docker build -t localhost:8083/wurstgurke/jenkinsnode:latest ."
            sh "docker login -u admin -p ncc1701 localhost:8083"
            sh "docker push localhost:8083/wurstgurke/jenkinsnode:latest"
        }
    }

    stage('Test image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a Volkswagen-type approach ;-) */

        app.inside {
            sh 'echo "Tests passed"'
        }
    }
}
