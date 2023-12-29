pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the Develop branch
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/develop']], userRemoteConfigs: [[url: 'https://github.com/hariagre/Random_color_Generator.git']]])
                }
            }
        }

        stage('Pull Content') {
            steps {
                // Pull content into a specific folder
                script {
                    dir('/home/ubuntu/Random_color_Generator') {
                        sh 'git pull origin develop'
                    }
                }
            }
        }

        // Add more stages as needed for your build, test, deploy steps
    }

    post {
        success {
            echo 'Pipeline successfully executed!'
        }
    }
}
