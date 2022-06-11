pipeline{
    agent{label 'built-in'}
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/SamirAllahverdi/SpringPetClinic.git'
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
                sh 'nohup java -jar /var/lib/jenkins/workspace/PetClinicDeclaritivePipeline/target/*.jar &'
            }
        }
        }
    }