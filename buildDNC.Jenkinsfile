def dockerImage;

node('DockerBI')
{
    stage('SCM')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/menaNosshy/JenkinsDocker.git']]]);
    }

    stage('Build')
    {
        dockerImage = docker.build('mnyaqoub/agent-dnc:v' + env.BUILD_NUMBER, './Dotnetcore');
    }

    stage('Push')
    {
        docker.withRegistry('https://index.docker.io/v1/', 'dockerhubcreds')
        {
            dockerImage.push();
        }
    }
}