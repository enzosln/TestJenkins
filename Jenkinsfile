pipeline {
    agent any
    stages {
        stage('Execute SSH Command') {
            steps {
                script {
                    // Récupération sécurisée de la clé SSH
                    withCredentials([sshUserPrivateKey(credentialsId: 'my_ssh_key', keyFileVariable: 'SSH_KEY_PATH', usernameVariable: 'SSH_USER')]) {
                        sh '''
                            ssh -o StrictHostKeyChecking=no -p 29371 -i $SSH_KEY_PATH $SSH_USER@enzo-salson.fr "touch /root/saluttest.txt"
                        '''
                    }
                }
            }
        }
    }
}
