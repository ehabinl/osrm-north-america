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
    stage('Osrm Extract') {
      steps {
        sh 'docker run -t -v "${PWD}:/data" osrm/osrm-backend osrm-extract -p /opt/car.lua /data/north-america-latest.osm.pbf'
      }
    }
    stage('OSRM Partition') {
      steps {
        sh 'docker run -t -v "${PWD}:/data" osrm/osrm-backend osrm-partition /data/north-america-latest.osrm'
      }
    }
    stage('OSRM Customize') {
      steps {
        sh 'docker run -t -v "${PWD}:/data" osrm/osrm-backend osrm-customize /data/north-america-latest.osrm'
        sh 'ls -laht .'
      }
    }
    stage('Chmod') {
      steps {
        sh 'chmod +r *'
      }
    }
  }
}