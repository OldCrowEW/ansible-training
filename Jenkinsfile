stage 'Checking connectivity'

node {
    deleteDir()
    checkout scm
    
    ansiblePlaybook(
        playbook: 'ping.yml',
        inventory: 'inventory.ini',
        credentialsId: '96b3fe82-e6a4-45eb-9e8d-0a512cba5a9c')
}

stage "Check syntax"

node {
    ansiblePlaybook(
        playbook: 'ping.yml',
        inventory: 'inventory.ini',
        credentialsId: '96b3fe82-e6a4-45eb-9e8d-0a512cba5a9c',
        extras: '--syntax-check --list-tasks'
        )
}