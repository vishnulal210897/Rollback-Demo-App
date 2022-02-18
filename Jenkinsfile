pipeline {
     agent any
stages {
    stage('git clone') {
       steps {
           git branch: 'main', url: 'https://github.com/vishnulal210897/Rollback-Demo-App.git'
        }
    }
    stage('Buil the code'){
        steps{
            echo 'Building the code.....'
        }
    }
    stage('Creating Artifact'){
        steps{
            archiveArtifacts artifacts: '**', excludes: 'Jenkinsfile', followSymlinks: false
            sh 'pwd' 
        }
    }

    stage('deploy the code on server'){
        steps{
            sh 'rm -r /var/www/html/sample/*'
            sh 'cp * /var/www/html/sample/'
            sh 'rm /var/www/html/sample/Jenkinsfile'
        }
    }
}
}
