pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                script {
                    bat './gradlew clean build'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                script {
                    bat './gradlew clean test'
                }
            }
        }
    }
}
