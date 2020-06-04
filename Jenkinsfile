pipeline {
    agent any
    stages { 
        stage('Example') {
            steps {
                echo 'Hello World'
                checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Git_Credentials', url: 'https://github.com/SandhyaSrunaj/javaparser-maven-sample.git']]]
                sh '''
                    ls 
                    pwd
                    cd /
                    pwd
                    ls
                    ./apache-maven-3.6.3/bin/mvn -f /var/lib/jenkins/workspace/test-pipeline/pom.xml clean package 
                '''
            }
        }
    }
}
