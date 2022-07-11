pipeline {
   agent any
   tools{
       maven 'M2_HOME'
       }

   stages {
	stage('Checkout') {
        steps {
		git 'https://github.com/devopscbabu/spring-petclinics.git'
               }
            }
      stage('Build my job') {
        steps {
            sh 'mvn clean compile'
               }
            }
      stage('Package you App') {
         steps{
             sh 'mvn clean package'
               }
            }
      stage('Build Image') {
            steps {
                script {
                    dockerImage = docker.build registry + "$Build_Number"
                }
            }
        }
    }
}
