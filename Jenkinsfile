pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                git branch: 'main',url: 'https://github.com/AnjuMeleth/SpringPetClinic.git'
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
      stage ('Package'){
          steps{
              sh 'mvn package'
          }
      }
      
      stage('Deploy'){
          steps{
              sh 'nohup java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar &'
          }
      }  
      }
    
}
