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

        sh "docker run nginx"
      }
    }
    stage("Integration") {
      when {
          branch "integration"
      }
      steps {
        println "Integration"
        println "Building and testing the container"

        sh "docker build . -t nginx"
      }
    }
    stage("PullRequest") {
      steps {
        if (env.CHANGE_ID) {
           steps {
             println "PullRequest"
             println "Building and testing the container"

             sh "docker build . -t nginx"
             sh "docker run -it -p 8081:8081 nginx"
             sh "curl localhost:8081"
           }
        }
      }
    }
  }
}