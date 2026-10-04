pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean verify'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn sonar:sonar -Dsonar.projectKey=student-project -Dsonar.projectName="StudentProject"'
                }
            }
        }
    }
}