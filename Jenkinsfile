pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                sh 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build Homies.sln --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test Homies.sln --no-build'
            }
        }
    }
}
