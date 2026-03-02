pipeline {
    agent any
    
    stages {
        stage('GIT') {
            steps {
                checkout scmGit(
                    branches: [[name: 'main']],
                    userRemoteConfigs: [[url: 'https://github.com/nasrerij/ahlembrikiii.git']]
                )
            }
        }
        stage('COMPILATION') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.projectKey=timesheet -Dsonar.host.url=http://localhost:9000 -Dsonar.login=sqa_ton_token_ici'
            }
        }
    }
}
