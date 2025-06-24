pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False' // disable host key checking
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: 'github-raz', url: 'https://github.com/raz-project/projectDev2.git'
            }
        }

        stage('Install Ansible Dependencies') {
            steps {
                sh '''
                    sudo apt update
                    sudo apt install -y ansible python3-pip
                    pip3 install docker
                    ansible-galaxy collection install community.docker
                '''
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    ansible-playbook -i inventory.ini project.yaml
                '''
            }
        }
    }
}
