pipeline {
  agent {
    node {
      label 'LocalServer'
    }

  }
  stages {
    stage('Get OSM raw data') {
      steps {
        sh '''#wget \'http://download.geofabrik.de/north-america-latest.osm.pbf\'
cp /home/ehab/Desktop/osrm/north-america-latest.osm.pbf north-america-latest.osm.pbf'''
        sh 'ls -lah *'
      }
    }
  }
}