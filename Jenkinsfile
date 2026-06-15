pipeline {
    agent any
    tools {
        jdk 'JDK17'
    }
    stages {
        stage('checkout') {
            steps {
            checkout scm
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
                
                export JENKINS_NODE_COOKIE=dontKillMe
                
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
