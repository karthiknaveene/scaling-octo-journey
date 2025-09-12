pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 2
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 3
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "Artifact-branch-5-1",
                    version: "1.0.2",
                    type: "docker",
                    url: "http://localhost:401",
                    digest: "6f637064707039346163663237383762",
                    label: "Test-artifact-5-1"
                )
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 2
                echo 'Running Integration Tests...'
                sleep 2
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 2
            }
        }
    }
}
