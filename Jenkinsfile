pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/padmavathi15/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with padma'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with padma'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with padma'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with padma'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
