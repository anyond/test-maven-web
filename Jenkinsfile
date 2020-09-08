pipeline {
    agent any
    stages {
        stage('CheckoutbyJenkinsfile') {
            steps {
                echo 'Checkout'
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a523af52-6a40-4791-a5aa-b7fa6b5b07bd', url: 'https://github.com/anyond/test-maven-web.git']]])
            }
        }
        stage('BuildfbyJenkinsfile') {
            steps {
                echo 'Build'
                sh 'mvn clean install'
            }
        }
        stage('SavebyJenkinsfile'){
            steps{
                echo 'Save'
                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }
    }
}