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
          stage('mvn unittest'){

            steps{

                script{
			sh 'mvn test'
                  }
                }
            }
	stage('mvn build'){

            steps{

                script{
                        sh 'mvn clean install'
                  }
                }
            }


  
      }
 }



