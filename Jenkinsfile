pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                bat 'ansible-playbook ansible/deploy.yml -i ansible/inventory.ini'
            }
        }

    }

    post {

        success {
            mail to: 'Sinavathtra01@gmail.com',
            subject: 'Build Success - SOEUN_Sereyvath',
            body: 'Website deployed: http://178.128.93.188/Midterm-2026/SOEUN_Sereyvath'
        }

        failure {
            mail to: 'Sinavathtra01@gmail.com',
            subject: 'Build Failed - SOEUN_Sereyvath',
            body: 'Build failed. Check Jenkins console output.'
        }

    }
}