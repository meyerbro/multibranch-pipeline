pipeline {
  agent { node { label 'jenkins-master' } }

  stages {
    stage("Master") {
      when {
          branch "master"
      }
      steps {
        println "Master"
        println "Running the container"
      }
    }
    stage("Integration") {
      when {
          branch "integration"
      }
      steps {
        println "Integration"
        println "Building and testing the container"
      }
    }
  }
}
