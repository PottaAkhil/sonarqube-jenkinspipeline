node {
  stage('Clone the Git') {
    git 'https://github.com/PottaAkhil/sonarqube-jenkinspipeline.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'sonarqube';
    withSonarQubeEnv('sonarqube') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=admin \
      -D sonar.projectKey=64ff26562ec686e6a6d6dd1a13ecb1e056ae4f00 \
      -D sonar.exclusions=vendor/**,resources/**,**/*.node \
      -D sonar.host.url=http://52.221.196.44:9000/"
    }
  }
}
