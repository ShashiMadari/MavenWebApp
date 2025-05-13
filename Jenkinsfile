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
            sh 'cp target/MymavenWebApp01.war /opt/tomcat/webapps/'
        }
    }
}


}
