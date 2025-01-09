pipeline {
    agent any
    tools {
        maven "maven"
        jdk "java"
    }
    stages {
        stage('GIT') {
            steps {
git branch: 'main', url: 'https://github.com/Daksh-2211/maven-jenkins6.git'            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archive artifact') {
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
                stage('Other build') {
            steps {
        build wait: false, job: 'deploy-pipepline'
            }
        }
    }
}
