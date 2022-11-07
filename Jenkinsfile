pipeline{
agent any

   stages{
    stage('Checkout GIT'){
                steps{
                    echo 'Pulling...';
                    git branch: 'main',
                    url : 'https://github.com/nourhenekheriji/DevOpsFront.git';
                             }
                             }

            stage('MVN CLEAN')
            {
                steps{
                sh  'mvn clean'
                }
            }
            stage('MVN COMPILE')
            {
                steps{
                sh  'mvn compile'
                }
            }


 stage('MVN SONARQUBE ')
                                            {
                                                steps{
                                                sh  'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=esprit'
                                                }
                                            }
                        stage('deploy nexus'){
                                                      steps{
                                                                 sh 'mvn  deploy'
                                                                     }
                                                               }

			    stage('Build docker image'){
                             steps{
                                 script{
                                    sh 'docker build -t nourhenekheriji/angular .'
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
                     	sh 'docker push nourhenekheriji/angular'
                        }  }

                        stage('Docker compose') {

                          steps {
                               sh 'docker-compose up -d'
                                 }  }


        }

      }