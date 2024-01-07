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
	stage('mvn build'){

            steps{

                        sh 'mvn clean install'
                  }
            }


  
      }
 }



