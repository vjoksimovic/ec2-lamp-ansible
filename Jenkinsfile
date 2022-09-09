pipeline {
	agent any
	stages {
                stage('Pull ansible prerequisites'){
                    steps{
                        git branch: 'main', credentialsId: 'ecr:eu-central-1:aws-credentials', url: 'https://github.com/ilekicgrid/Ansible-for-jenkins.git'
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
