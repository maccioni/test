pipeline {
    agent any

    stages {
        stage('Check enviroment') {
            steps {
              echo "Check running user"
              sh "whoami"
              sh "who am i"
              echo "Check local directory"
              sh "ls -l"
              echo "Check enviroment variables"
              sh "env"
            }
        }
        stage('Configure VLANs on Cisco NX-OS') {
            steps {
              echo "Running Ansible playbook on Cisco NX-OS"
              script {
                    try {
                      sh "ansible-playbook nx-vlan.yaml --extra-vars "ansible_user=admin ansible_password=C!sco123 expected_check_status=PASS"
                    } catch (error) {
                    error("Ansible Playbook failed!!!")
                    }
                }
            }
        }
    }
}
