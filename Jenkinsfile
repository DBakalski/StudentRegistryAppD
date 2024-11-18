pipeline{
    agent any

    environment{
        NODE_VERIONS = '22.x'
    }

    tools{
        nodejs '${NODE_VERIONS}'
    }

    stages{
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
        stage(Ïnstall dependancies){
            steps{
                script{
                    if(isUnix()){
                        sh 'npm install'
                    }
                    else{
                        sh 'npm install'
                    }
                }
            }

        }

        stage('start Aplication and run test'){
            steps{
                script{
                    sh 'npm start &'
                    sh 'wait-on http://localhost:8090'
                    sh 'npm test'
                }
            }
        }
    }

    post {
        always{
            echo "CI pipeline completed"
        }

    }
}