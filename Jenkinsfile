
// Get the next release version 


pipeline {
  agent any
  

  environment {
    GITLAB_HOST = "github.com"
    CREDENTIALS_ID = "gitlab-ssh-jenkins"
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
              }
            }
            }
            }

          }
}