pipeline {
	agent any
	stages {
		stage('Checkout') {
                    steps {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vjoksimovic/jenkins-tf-lamp']]])

                  }
                }

            stage('Start application with Ansible') {
                        steps {
                            script {
                                ansiblePlaybook credentialsId: 'ansible-jenkins', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts.yml', playbook: 'sites.yml'
                            }
                        }
                    }
	}
}
