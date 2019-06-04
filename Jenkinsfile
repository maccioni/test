pipeline {
    agent any

    stages {
        stage('Update code from GitHub') {
            steps {
              echo "Check enviroment "
              sh "whoami"
              sh "who am i"
              sh "ls -l"
              sh "env"
              echo "Pull code from GitHub"
              sh 'git pull origin master'
            }
        }
        stage('Configure VLANs on Cisco NX-OS') {
            steps {
              echo "Running Ansible playbook on Cisco NX-OS"
              script {
                    try {
                      sh 'ansible-playbook nx-vlan.yaml --extra-vars "ansible_user=admin ansible_password=C!sco123 expected_check_status=PASS"'
                    } catch (error) {
                    error("Ansible Playbook failed!!!")
                    }
                }
            }
        }
    }
}
