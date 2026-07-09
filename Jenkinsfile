pipeline {
     agent any
     tools {
         maven 'Maven'
     }
     stages {
          stage("Checkout") {
               steps {
                    git url: 'https://github.com/DanielMojekwu425/calculator.git', branch: 'main'
               }
          }

           stage("compile") {
               steps {
                   bat 'mvn clean compile'
               }
          }
          stage("Unit test") {
               steps {
                   bat "./mvnw test"
               }
          }
          stage("Code coverage") {
               steps {
                    bat "./mvnw verify"
                    bat "./mvnw test jacoco:check"
           }
          }
     }
}