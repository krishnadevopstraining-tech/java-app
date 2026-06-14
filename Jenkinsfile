pipeline {
    agent any
    tools {
        jdk 'JDK17'
    }
    stages {
        stage('checkout') {
            steps {
            git branch: 'main', url: 'https://github.com/krishnadevopstraining-tech/java-app.git'
            }
        }

        stage('build') {
            steps {
            sh 'java --version'
            sh 'mvn clean package -DskipTests'
            }
        }

        stage('test') {
            steps {
            sh 'mvn test'
            }
        }

        stage('deploy') {
            steps {
                sh '''
                pwd
                whoami
        
                ls -lh target/
        
                nohup java -jar target/krishna-devops-training-0.0.1-SNAPSHOT.jar \
                --server.port=8081 > app.log 2>&1 &
        
                sleep 15
        
                echo "===== JAVA PROCESSES ====="
                ps -ef | grep java
        
                echo "===== APP LOG ====="
                cat app.log || true
                '''
            }
        }
    }
}
