pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
deploy adapters: [tomcat9(credentialsId: '0e04234c-bdb4-4ec1-9063-ac61cafc40d7', path: '', url: 'http://13.57.41.218:8080/')], contextPath: 'webpp', war: '**/*.war'            }
        }
    }
}
