node('UBUNTU_NODE2') {
    stage('vcs'){
        git url: 'https://github.com/srikanthvelma/MusicStore.git',
            branch: 'main'  
    }
    stage('Build') {
        sh 'dotnet build ./MusicStore/MusicStore.csproj',
        sh 'dotnet test ./MusicStore/MusicStore.csproj --logger:"junit;LogFilePath=test-result.xml" '
    }
    stage('publish results') {
        junit testResults: 'MusicStoreTest/*.xml'
        allowEmptyResults: true
    }
}
