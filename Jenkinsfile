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
               git branch: 'main', credentialsId: '1c4f9df9-a43c-4b66-b22b-da4ec814c95b', url: 'git@github.com:arsenii-fv/netology_9.4_playb.git' 
            }
        }
        stage("download molecule") {
            steps {
                sh 'pip3 install molecule molecule_docker'
            }
        }
        stage("run molecule") {
            steps {
                sh 'ls -l'
                //sh 'molecule test'
            }
        }
    }
}
