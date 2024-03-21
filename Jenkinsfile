pipeline {
  agent {
    any {
      image 'hashicorp/packer:latest'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' // mount Docker socket to access the host's Docker daemon
    }
  }

  stages {
    stage("Initialize Packer") {
      steps {

        sh "packer init"
      }
    }
  }
    stage("Building AMI") {
      steps {

        sh "packer build aws-ami-v1.pkr.hcl"
      }
    }
}