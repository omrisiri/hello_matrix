// properties([pipelineTriggers([cron('H/5 * * * *')])])

node('docker') {
    stage('stage1'){
      echo 'Hello World'
    }
    stage('stage2'){
        myname = "omri 3"
        parallel firstBranch: {
          def myname = 'omri'
          echo "Hello ${myname}"
        }, secondBranch: {
          def myname = 'omri 2'
          echo "Hello ${myname} in parallel"
       }
      echo "Hello ${myname}"
    }
    stage('theend'){
       println('Goodbye world') 
    }
}
