pipeline {
    agent { lable 'docker'}
    triggers {
        pollSCM('* 23 * * 1-5')
    }
    stages {
        stage ('vcs') {
            steps {
                git url: https://github.com/Sravyaws/StudentCoursesRestAPI.git
                    branch spring_1_release
            }
        }
        stage ('build') {
            steps {
                sh 'docker image build -t <dockerhubusername>/spc:latest .'

            }
            
            
        }
        stage ('scan and push') {
            steps {
                sh 'echo docker scan image sravya18/src:latest'
                sh 'docker image push sravya18/src:latest'
            }
            
        }
    }
}