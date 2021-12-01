pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                script {
                    sh './gradlew clean build'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                script {
                    sh './gradlew clean test'
                }
            }
        }
    }
}
