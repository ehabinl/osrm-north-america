pipeline {
  agent {
    node {
      label 'LocalServer'
    }

  }
  stages {
    stage('Get OSM raw data') {
      steps {
        sh 'wget \'https://www.google.com/logos/doodles/2019/grandparents-day-2019-italy-5423245699317760-2x.jpg\''
        sh 'ls -lah *'
      }
    }
  }
}