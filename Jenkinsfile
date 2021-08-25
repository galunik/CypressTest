pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                bat 'npm install'
            }
        }
        stage('parallel') {
            parallel {
                // start several test jobs in parallel, and they all
                // will use Cypress Dashboard to load balance any found spec files
                stage('Run tests in parallel A') {
                    steps {
                        bat 'npx cypress run --record --key 796f0713-2f6e-4650-b445-d43b7fecd62b --parallel'
                    }
                }
                stage('Run tests in parallel B') {
                    steps {
                        bat 'npx cypress run --record --key 796f0713-2f6e-4650-b445-d43b7fecd62b --parallel'
                    }
                }
            }
        }
    }
}