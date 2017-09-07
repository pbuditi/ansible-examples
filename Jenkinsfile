pipeline {
    agent { label 'ubuntu_agent' }
    triggers {
        pollSCM("")
    }
    stages {
        stage('Deploy') {
            steps {
               script {
                    ansiblePlaybook credentialsId: 'pradeep-windows', inventory: 'win-ansible/hosts', playbook: 'win-ansible/site.yml', sudoUser: null
                }
            }
        }
    }  	    
	    
    post {
        always {
            sh 'echo tests'
        }
    }
}
