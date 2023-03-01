node('UBUNTU_NODE2') {
    stage('vcs'){
        git url: 'https://github.com/srikanthvelma/MusicStore.git',
            branch: 'main'  
    }
    stage('Build') {
        sh 'dotnet build ./MusicStore/MusicStore.csproj'
    }
    stage('publish results') {
        junit testResults: 'MusicStoreTest/*.xml'
        allowEmptyResults: true
    }
}
