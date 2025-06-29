pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: 'github-raz', url: 'https://github.com/raz-project/projectDev2.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    ansible-playbook -i inventory.ini project.yaml --private-key=/var/lib/jenkins/.ssh/id_rsa -u worker
                 '''
            }  
        }
    }
}
