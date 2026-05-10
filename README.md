pipeline { 
    agent any 
 
    tools { 
        maven 'Maven' 
        jdk 'JDK' 
    } 
 
    stages { 
 
        stage('Checkout') { 
            steps { 
                git branch: 'main', 
                url: URL 
            } 
        } 
 
        stage('Build') { 
            steps { 
                bat 'mvn clean package' 
            } 
        } 
    } 
} 
