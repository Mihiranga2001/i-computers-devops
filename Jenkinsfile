pipeline {

    agent any


    environment {

        DOCKER_USERNAME = credentials('dockerhub')

    }


    stages {


        stage('Checkout DevOps Repository') {

            steps {

                echo 'Downloading DevOps files'

                git branch: 'devops',
                url: 'https://github.com/Mihiranga2001/i-computers-devops.git'

            }

        }



        stage('Clone Frontend') {

            steps {

                echo 'Cloning frontend repository'

                sh '''

                rm -rf i-computers-frontend

                git clone -b devops \
                https://github.com/Mihiranga2001/i-computers-frontend.git

                '''

            }

        }



        stage('Clone Backend') {

            steps {

                echo 'Cloning backend repository'

                sh '''

                rm -rf i-computers-backend

                git clone -b devops \
                https://github.com/Mihiranga2001/i-computers-backend.git

                '''

            }

        }



        stage('Install Frontend Dependencies') {

            steps {

                echo 'Installing frontend packages'

                sh '''

                cd i-computers-frontend

                npm install

                '''

            }

        }



        stage('Install Backend Dependencies') {

            steps {

                echo 'Installing backend packages'

                sh '''

                cd i-computers-backend

                npm install

                '''

            }

        }



        stage('Run Tests') {

            steps {

                echo 'Running backend tests'

                sh '''

                cd i-computers-backend

                npm test || true

                '''

            }

        }



        stage('Build Docker Images') {

            steps {

                echo 'Building Docker images'

                sh '''

                docker build \
                -t gaurawawickramasinghe/icomputers-frontend:latest \
                ./i-computers-frontend



                docker build \
                -t gaurawawickramasinghe/icomputers-backend:latest \
                ./i-computers-backend

                '''

            }

        }



        stage('Login Docker Hub & Push Images') {

            steps {


                withCredentials([

                    usernamePassword(

                        credentialsId: 'dockerhub',

                        usernameVariable: 'DOCKER_USER',

                        passwordVariable: 'DOCKER_PASS'

                    )

                ])


                {


                    sh '''

                    echo "Logging into Docker Hub"


                    docker login \
                    -u $DOCKER_USER \
                    -p $DOCKER_PASS



                    echo "Pushing frontend image"


                    docker push \
                    gaurawawickramasinghe/icomputers-frontend:latest



                    echo "Pushing backend image"


                    docker push \
                    gaurawawickramasinghe/icomputers-backend:latest


                    '''

                }

            }

        }




        stage('Deploy Application') {


            steps {


                echo 'Deploying using Docker Compose'


                sh '''

                docker compose down || true


                docker compose up -d


                '''

            }

        }


    }



    post {


        success {

            echo 'Pipeline completed successfully 🚀'

        }


        failure {

            echo 'Pipeline failed ❌'

        }


    }

}