properties([pipelineTriggers([cron('H/5 * * * *')])])

node {
    stage('stage1'){
      echo 'Hello World'
    }
    stage('stage2'){
        parallel firstBranch: {
          def myname = 'omri'
          echo "Hello ${myname}"
        }, secondBranch: {
          def myname = 'omri'
          echo "Hello ${myname} in parallel"
       }
      def myname = 'omri'
      echo "Hello ${myname}"
    }
    stage('theend'){
       println('Goodbye world') 
    }
}
