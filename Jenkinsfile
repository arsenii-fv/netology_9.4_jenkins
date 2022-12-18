pipeline {
    agent {
        label 'linux'
    }
    // options {
    //     timestamps
    // }
    stages {
        stage("Checkout SCM") {
            steps {
                dir ('roles_g') {
                    git branch: 'main', credentialsId: '1c4f9df9-a43c-4b66-b22b-da4ec814c95b', url: 'git@github.com:arsenii-fv/netology_9.4_playb.git' 
                }
            }
        }
        stage("download molecule") {
            steps {
                sh 'pip3 install molecule==3.3.4 molecule_docker==0.3.3'
                //sh 'pip uninstall urllib3'
                // sh 'pip3 install chardet'
                //sh 'pip install --upgrade pip'
            }
        }
        stage("run molecule") {
            steps {
                dir ('roles_g/roles/vector_role/') {
                   sh 'molecule test'
                }    
            }
        }
    }
}
