pipeline {
    agent any
    
    tools {
        maven 'Maven'
    }
    
    environment {
        SONAR_HOST = 'http://localhost:9000'
        SONAR_TOKEN = 'sqa_ton_token_ici'
    }
    
    stages {
        stage('GIT') {
            steps {
                git 'https://github.com/nasrerij/ahlembrikiii.git'
            }
        }
        stage('COMPILATION') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.projectKey=timesheet -Dsonar.host.url=$SONAR_HOST -Dsonar.login=$SONAR_TOKEN'
            }
        }
    }
}
