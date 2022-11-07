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

    

			    stage('Build docker image'){
                             steps{
                                 
                                    sh 'docker build -t nourhenekheriji/angular .'
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