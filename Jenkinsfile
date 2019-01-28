pipeline {
    agent any
    tools{
maven 'Maven 3.6.0'
}
        stages {
        stage('Clone and Clean') { 
            steps {
                sh '''
echo "PATH = ${PATH}"
echo "M2_HOME = ${M2_HOME}"
'''
        sh "export PATH=$PATH:$HOME/bin:/terraform:/terraform/eks:/usr/bin:/root/firefox/gtk+-3.20.0:/root/apache-maven-3.6.0/bin"
        sh "mvn clean"
            }
        }
        stage('Test') { 
            steps {
                sh "mvn test" 
            }
        }
        stage('Deploy') { 
            steps {
                sh "mvn package"
            }
        }
    }
}

