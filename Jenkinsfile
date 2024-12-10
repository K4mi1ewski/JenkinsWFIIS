pipeline {
    agent any
    triggers {
        pollSCM 'H/5 * * * *'
    } // Use any available Jenkins agent
    stages {
        // stage('Checkout') {
        //     steps {
        //         // Checkout code from version control
        //         git branch: 'main',
        //             url: 'https://github.com/K4mi1ewski/JenkinsWFIIS.git'
        //     }
        // }
        stage('Build') {
            steps {
                // Example build command
                echo "Stage -> build"
                sh 'ls -la'
                sh 'echo "Hello there" > hello.txt'
                sh 'cat README.md'
            }
        }
        stage('Test') {
            steps {
                // Example test command
                echo "Stage->test"
                sh 'ls -la'
                sh 'cat hello.txt'
            }
        }
        stage('Package') {
            steps {
                // Example packaging command
                echo "Stage -> package"
               // sh 'zip -r artifact.zip build/' // Replace with your packaging command
                //archiveArtifacts artifacts: 'artifact.zip', fingerprint: true
            }
        }
        stage('Deploy') {
            steps {
                // Example deploy command
                echo 'Deploying to environment...'
                // Replace with your deploy command (e.g., scp, kubectl apply)
            }
        }
    }
    post {
        always { // Actions to always run (e.g., cleanup, notifications)
            echo 'Pipeline execution complete.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}