pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Build"
                // Ejecutar el build de tu aplicación
                //sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                echo "Test"
                // Ejecutar las pruebas de tu aplicación
                //sh 'mvn test'
            }
        }
        
        stage('SonarQube analysis') {
            steps {
                script {
                    // Configurar el entorno de SonarQube
                    // def scannerHome = tool 'SonarScanner 4.0'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner \
                        -Dsonar.projectKey=Modulo3 \
                        -Dsonar.projectName=Modulo3 \
                        -Dsonar.sources=src/main/java/ \
                        -Dsonar.java.binaries=./target/classes"
                    }
                }
            }
        }
    }
}
