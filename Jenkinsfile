node('UBUNTU_NODE2') {
    stage('vcs'){
        git url: 'https://github.com/srikanthvelma/MusicStore.git',
            branch: 'main'  
    }
    stage('Build') {
        sh 'dotnet build ./MusicStore/MusicStore.csproj'
    }
    stage('test') {
        sh 'dotnet test ./MusicStoreTest/MusicStoreTest.csproj --logger:"junit;LogFilePath=TEST-result.xml"'
    }
    stage('publish results') {
        junit testResults: 'MusicStoreTest/TEST-*.xml',
        allowEmptyResults: true
    }
}
