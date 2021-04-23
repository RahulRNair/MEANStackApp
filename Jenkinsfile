node('docker'){
  stage('SCM') {
    checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: 'refs/heads/develop']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/RahulRNair/MEANStackApp.git']]]
  }
  stage('SonarQube Analysis') {
        sh "/var/jenkins_home/tools/hudson.plugins.sonar.SonarRunnerInstallation/scanner4.6/bin/sonar-scanner -Dsonar.host.url=http://localhost:9000 -Dsonar.projectName=test -Dsonar.projectVersion=1.0 -Dsonar.projectKey=test -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/sonar-test1"
    }
}
