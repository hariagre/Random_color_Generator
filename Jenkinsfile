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
        script {
            dir('/var/lib/jenkins') {
                def gitOutput = sh(script: 'git pull origin develop', returnStatus: true).trim()
                echo "Git Output: ${gitOutput}"
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
