pipeline{
    agent{label 'principal'}
    tools{
        maven 'M3'
        jdk 'jdk8'
    }
    stages{
        stage('Checkout'){
            steps{ 
                git branch: 'main', url: 'https://github.com/kpedrozaqa/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }    
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /Users/karinapedroza/.jenkins/workspace/PetClinicDeclaratedPipeline/target/*.jar'
            }
        }
    }
}
