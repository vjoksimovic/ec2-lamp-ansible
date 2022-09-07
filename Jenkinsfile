pipeline {
	agent any
	stages {
		stage('Pull Ansible repository') {
                        steps {
                            script {
                                git 'https://github.com/vjoksimovic/ec2-lamp-ansible.git'
                            }
                        }
                    }

            stage('Start application with Ansible') {
                        steps {
                            script {
                                ansiblePlaybook credentialsId: 'ansible-jenkins', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts.yml', playbook: 'main.yml'
                            }
                        }
                    }
	}
}
