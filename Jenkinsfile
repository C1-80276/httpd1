pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh 'docker image build -t chiraag77/chiraag_repo:forAws .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_PaLl5Fxzkq8et76Hg8CaWv9__SQ | docker login -u chiraag77 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh 'docker image push chiraag77/chiraag77:forAws'
            }
        }
        stage ('reload docker service') {
            steps {
                sh 'docker service update --image chiraag77/chiraag_repo:forAws --force awsService'
            }
        }

    }
}
