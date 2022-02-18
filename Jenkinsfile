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

    //stage('deploy the code on server'){
        //steps{
          //  sshPublisher(publishers: [sshPublisherDesc(configName: 'stage', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'var/www/rollback-demo/' , remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
        //}
    //}
}
}
