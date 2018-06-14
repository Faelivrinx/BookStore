pipeline {
     agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'whoami'
                //sh '/usr/local/bin/docker ps'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                //sh 'mvn test'
                sh 'echo "test"'
            }
            post {
                always {
                    //junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh 'deliver.sh'
            }
        }
    }
}
