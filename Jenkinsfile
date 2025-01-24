pipeline {
    agent any
    stages {
        stage('GIT') {
            steps {
git branch: 'main', url: 'https://github.com/Daksh-2211/maven-jenkins6.git'            }
        }
        stage('Build') {
            steps {
                sh '''docker build -t dakshbhavsar/maven_test:v${BUILD_NUMBER} .
                      docker tag dakshbhavsar/maven_test:v${BUILD_NUMBER} dakshbhavsar/maven_test:latest
                      docker push dakshbhavsar/maven_test:v${BUILD_NUMBER}
                      dakshbhavsar/maven_test:latest '''
                                      
                
            }
        }

    }
}
