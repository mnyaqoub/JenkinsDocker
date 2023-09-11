node('Dotnetcore')
{
    stage('SCM')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/menaNosshy/dotnetwebapp.git']]]);
    }

    stage('Build')
    {
        sh 'dotnet build .'
    }

    stage('Test')
    {
        echo 'Excute unit tests'
    }

    stage('Package')
    {
        echo 'Zip it up'
    }

    stage('Deploy')
    {
        echo 'Push to deployment'
    }

    stage('Archive')
    {
        archiveArtifacts artifacts: 'dotnetwebapp/*.*'
    }
}