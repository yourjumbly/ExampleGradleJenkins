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
        
        stage('Publish Test Coverage Report') {
         steps {
           step([$class: 'JacocoPublisher', 
                execPattern: '**/build/jacoco/*.exec',
                classPattern: '**/build/classes',
                sourcePattern: 'src/main/java',
                exclusionPattern: 'src/test*'
                ])
            }
        }
    }
    post {
      always {
        junit '**/test-results/test/*.xml'
      }
   } 
}
