pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ShashiMadari/MavenWebApp.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy WAR') {
            steps {
                sh '''
                    # Step 1: Copy WAR to /tmp on remote server
                    scp -o StrictHostKeyChecking=no target/MymavenWebApp01.war shruthi@172.18.19.169:/tmp/

                    # Step 2: SSH into the server and move it with sudo
                    ssh -o StrictHostKeyChecking=no shruthi@172.18.19.169 "sudo mv /tmp/MymavenWebApp01.war /opt/tomcat/webapps/"
                '''
            }
        }
    }
}
