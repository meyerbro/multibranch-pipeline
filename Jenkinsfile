pipeline {
  stage("Master") {
    when {
        branch "master"
    }
    println "Master"
    println "Running the container"
  }
  stage("Integration") {
    when {
        branch "integration"
    }
    println "Integration"
    println "Building and testing the container"
  }
}
