pipeline{
    agent any
    tools{
        name: 'MavenNew', type: 'maven'
    }
    stages{
        stage('clone Repo') {
            steps{
              git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            } 
}
        stage('Code build') {
           steps{
            sh 'mvn package'
           }
    }
        stage('code deploy'){
            steps{
              deploy adapters: [tomcat9(credentialsId: 'tomcatcredentials', path: '', url: 'http://3.88.217.44:8080')], contextPath: null, war: '**/*.addressbook'
            }

    }
}
}
