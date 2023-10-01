pipeline{
    agent none
    environment {
        DOCKERHUB_CREDENTIALS=credentials('')
    }
    
    stages{
        stage('Hello'){
            agent{ 
                label 'Kub-master'
            }
            steps{
                echo 'Hello World'
            }
        }
        stage('git'){
            agent{ 
                label 'Kub-master'
            }

            steps{

                git''
            }
        }
        stage('docker') {
            agent { 
                label 'Kub-master'
            }

            steps {

                sh ''
                sh 'sudo echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh ''

            }
        }
        stage('Kuberneets') {
            agent { 
                label 'Kub-master'
            }

            steps {

                sh 'sudo kubectl create -f deployment.yml'
                sh 'sudo kubectl create -f service.yml'
            }
        }        
        
    }
}
