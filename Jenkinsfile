node('aws-slaves') {
    stage ('Git checkout') {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kishoregp/sample-maven-app.git']]])
    }
    stage('Unit Test') {
        sh '''
            mvn test
        '''
    }
    stage('Maven Build') {
        sh '''
            mvn clean install
        '''
    }
}
