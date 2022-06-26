pipeline {
    agent any 
    stages {
        stage('clone repo and clean') {
            steps {
                bat "if exist maven_jenkins2 rmdir /s /q maven_jenkins2"
                bat "git clone https://github.com/Manav-Kapila/maven_jenkins2.git" 
                bat "mvn clean -f maven_jenkins2"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f maven_jenkins2" 
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn package -f maven_jenkins2"
            }
        }
    }
}
