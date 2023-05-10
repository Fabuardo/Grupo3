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
    }
}
