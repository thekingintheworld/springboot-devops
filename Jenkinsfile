pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh './mvnw clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cd ansible && ansible-playbook -i inventory.ini deploy.yml'
            }
        }

    }

    post {

        success {
            mail to: 'Sinavathtra01@gmail.com',
            subject: "Build Success",
            body: "Website deployed successfully: http://178.128.93.188/Midterm-2026/SOEUN_Sereyvath"
        }

        failure {
            mail to: 'Sinavathtra01@gmail.com',
            subject: "Build Failed",
            body: "The Jenkins build failed. Please check Jenkins logs."
        }

    }
}         
