pipeline {
    agent any

    stages {
        stage('Build Sample App') {
            steps {
                echo 'Building the sample app...'
                sh 'bash ./sample-app.sh'
            }
        }

        stage('Test Sample App') {
            steps {
                echo 'Testing the sample app...'
                sh '''
                    APP_IP=172.17.0.3
                    JENKINS_IP=172.17.0.2
                    sleep 5
                    curl http://$APP_IP:5050/ | grep "You are calling me from $JENKINS_IP"
                '''
            }
        }
    }
}
