pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Clone'){
            steps{
                git 'https://github.com/hungnd6282/reactjs-jenkins.git'
            }
        }
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        // stage("Deploy") {
        //     steps {
        //         sh "rm -rf /var/www/jenkins-react-app"
        //         sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
        //     }
        // }
    }
}