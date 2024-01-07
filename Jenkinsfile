pipeline{

    agent any

    stages {

        stage('Git Checkout'){

            steps{

                script{

                   git branch: 'main', url: 'https://github.com/pramodmr31/demo-counter-app.git'
                  }
                }
            } 
      stage('UNIT testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn test'
                }
            }
        }
        stage('Integration testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn verify -DskipUnitTests'
                }
            }
        }
	stage('mvn build'){

            steps{

                        sh 'mvn clean install'
                  }
            }

         stage('docker image build'){

            steps{
                   script{
                        sh 'docker build -t $JOB_NAME:v1.$BUILD_ID'
			sh 'docker tag $JOB_NAME:v1.$BUILD_ID pramod284/demoproject_1:$BUILD_ID'
			 }
                  }
            }
	  stage('push the image to docker hub'){

            steps{
                   script{
         withCredentials([string(credentialsId: 'docker_cred', variable: 'Dockerhub_Cred')])
			sh 'docker login -u pramod284 -p $(Dockerhub_Cred)'
			sh 'docker image push pramod284/demoproject_1:$BUILD_ID'  
			}
                  }
            }


  
      }
 }



