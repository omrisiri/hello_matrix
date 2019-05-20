docker

node('docker') {
    stage('stage1'){
      echo 'Hello World'
    }
    stage('stage2'){
        myname = "omri 3"
          checkout scm
        parallel firstBranch: {
          def myname = 'omri'
          sh 'ls -la '
          echo "Hello ${myname}"
        }, secondBranch: {
          def myname = 'omri 2'
          sh 'ls -la '
          echo "Hello ${myname} in parallel"
       }
      echo "Hello ${myname}"
    }
    stage('theend'){
        node('master') {
           git 'https://github.com/heroku/node-js-sample.git'
           sh 'ls -la '
           println('Goodbye world') 
        }
    }
}
