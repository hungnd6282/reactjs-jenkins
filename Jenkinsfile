pipeline {
    agent any
    stages {
        stage('Clone'){
            steps{
                git 'https://github.com/hungnd6282/reactjs-jenkins.git'
            }
        }
        stage("Build") {
            steps {
                 sh "sudo node -v"
                 sh "sudo npm -v"
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo -i"
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}