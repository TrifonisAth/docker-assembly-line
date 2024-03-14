pipeline {
    agent {
        docker {
            image 'maven'
            label 'my-docker-agent'
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket for Docker inside Docker
        }
    }

    stages {
        stage('maven') {
            steps {
                sh "mvn -version"
                sh "java -version"
                sh "docker --version" // Verify Docker executable is available
            }
        }
    }
}
