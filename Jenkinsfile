pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
              git 'https://github.com/eknaprasath/maven-project.git'
            }
        }
        stage('build') {
            steps {
               // sh 'mvn --version'
               sh 'mvn clean install -DskipTests'
            }
        }
        stage('SonarQube analysis 1') {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('command') {
           steps {
                sh '''pwd
                      cd
                      ls
                    whoami'''
            }
        }  
    }
}
