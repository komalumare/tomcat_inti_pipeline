pipeline {
    agent any

    stages {
        stage('clean') {
            steps {
                bat 'mvn clean'
            }
        }
      stage('package') {
            steps {
                bat 'mvn package'
            }
        }
      stage('tomcat') {
            steps {
               deploy adapters: [tomcat8(credentialsId: '8f9e4a48-90b7-4b3e-a2d3-6e6706eb89ae', path: '', url: 'http://localhost:8282/')], contextPath: 'pipeline_tomcat_inti', war: '**/*.war'
            }
        }
    }
}
