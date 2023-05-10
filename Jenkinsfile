pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
        //        sh 'mvn clean package'
        echo "Build"
            }
        }
        stage('Test') {
            steps {
        //      sh 'mvn test'
         echo "Test"
            }
        }
        /*stage('SonarQube analysis') {
            def scannerHome = tool 'SonarScanner 4.0';
            withSonarQubeEnv('SonarQube') { // If you have configured more than one global server connection, you can specify its name
            sh "${scannerHome}/bin/sonar-scanner"
            }
         }*/
        stage('SonarQube analysis') {
             steps {
                 withSonarQubeEnv('SonarQube'){
                //SCANNER_HOME = tool 'SonarScanner 4.0';
                }
            steps {
              withSonarQubeEnv(credentialsId: 'sqp_02b7d5fc6b37dceb7a1475b3241fef9fa793e2c8', installationName: 'SonarQube') {
              sh '''$SCANNER_HOME/bin/sonar-scanner \
              -Dsonar.projectKey=Modulo3 \
            -Dsonar.projectName=Modulo3 \
               -Dsonar.sources=src/main/java/ \
               -Dsonar.java.binaries=./target/classes \
             //-Dsonar.exclusions=src/test/java/**/*.java \
             //-Dsonar.projectVersion=${BUILD_NUMBER}-${GIT_COMMIT_SHORT}'''
             }
            }
            }
        }
    }
}
