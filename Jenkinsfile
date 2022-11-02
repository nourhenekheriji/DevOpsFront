pipeline{
agent any

        stages{




			    stage('Build docker image'){
                             steps{
                                 script{
                                    sh 'docker build -t nourhenekheriji/angularproject .'
                                 }
                             }
                         }




      stage('Docker login') {

                                         steps {
                                          sh 'echo "login Docker ...."'
                   	sh 'docker login -u nourhenekheriji -p Nourhene1234'
                               }  }
		 stage('Docker push') {

                 steps {
                      sh 'echo "Docker is pushing ...."'
                     	sh 'docker push nourhenekheriji/angularproject'
                        }  }

                        stage('Docker compose') {

                          steps {
                               sh 'docker-compose up -d'
                                 }  }


        }

      }