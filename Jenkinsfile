
pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Sach791/MymavenwebApp.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy WAR Locally') {
            steps {
                sh '''
                    # Local copy to Tomcat webapps directory
                    sudo cp target/MymavenwebApp.war /opt/tomcat/webapps/
                '''
            }
        }
    }
}
