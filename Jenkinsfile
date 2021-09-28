pipeline {
    agent any

    stages {
        stage('gitcheckout') {
            steps {
              checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/lakhan361/hello-world.git']]])
            }
        }
        stage('buildit') {
            steps {
              sh '''chmod +x  ./testscript.sh
              ./testscript.sh > scriptfile.txt'''
            }
        }
        stage('post') {
            steps {
             archiveArtifacts artifacts: 'scriptfile.txt'
            }
        }
    }
}
