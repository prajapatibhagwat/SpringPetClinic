pipeline{
    agent{
        label 'built-in'
    }
    tools{
        maven 'M3'
    }
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/prajapatibhagwat/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Package'){
            steps{
                bat 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
               dir("${WORKSPACE}/target") {
                    bat "java -jar spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar"
                }
            }
        }
    }
}
