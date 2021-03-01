
// Get the next release version 
def nextVersionFromGit(scope) {
    def latestVersion = sh returnStdout: true, script: 'git describe --tags "$(git rev-list --tags=*.*.* --max-count=1 2> /dev/null)" 2> /dev/null || echo 0.0.0'
    def (major, minor, patch) = latestVersion.tokenize('.').collect { it.toInteger() }
    def nextVersion
    switch (scope) {
        case 'major':
            nextVersion = "${major + 1}.0.0"
            break
        case 'minor':
            nextVersion = "${major}.${minor + 1}.0"
            break
        case 'patch':
            nextVersion = "${major}.${minor}.${patch + 1}"
            break
    }
    nextVersion
}

pipeline {
  agent any
  

  environment {
    GITLAB_HOST = "github.com"
    CREDENTIALS_ID = "gitlab-ssh-jenkins"
    INFRA_REPO_LIST = "gvms-k8s-core gvms-terraform-code"
    RELEASE_VERSION = "version_place_holder"

  }
      stages {
        stage('Data Request Portal') {
          stages {
            stage('Build CI Image') {
              steps {
                sh '''
                        echo "dockerbuild Data Request Portal with GIT COMMIT TAG: ${GIT_COMMIT} "
                        echo "**************************************"
                        
                '''
                nextVersionFromGit(patch)
              }
            }
            }
            }

          }
}