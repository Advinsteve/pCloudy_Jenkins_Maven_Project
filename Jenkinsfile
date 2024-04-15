pipeline {
    agent any
    
    environment {
        MAVEN_HOME = "/usr/share/maven" 
        PATH = "$PATH:$MAVEN_HOME/bin"
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}

