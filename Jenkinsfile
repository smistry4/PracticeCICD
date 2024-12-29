pipeline {
    agent {
        label 'spring-node' // Specify the Jenkins agent with the label "spring-node"
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Fetching code from Git repository...'
                checkout scm // Fetch code from the repository configured in the job
            }
        }

        stage('Build with Maven') {
            steps {
                echo 'Building project with Maven...'
                sh 'mvn clean package' // Use Maven to clean and build the project
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed. Check the logs for details.'
        }
    }
}
