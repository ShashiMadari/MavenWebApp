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
            // Replace with your actual remote details
            sh 'scp -o StrictHostKeyChecking=no target/MymavenWebApp01.war shruthi@172.18.19.100:/path/to/tomcat/webapps/'
        }
    }
}


}
