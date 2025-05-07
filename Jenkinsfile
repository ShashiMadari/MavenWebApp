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
            sh 'scp target/MymavenWebApp01.war shruthi-VirtualBox@127.0.1.1:/path/to/tomcat/webapps/'
        }
    }
}


}
