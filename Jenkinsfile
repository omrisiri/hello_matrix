properties([pipelineTriggers([cron('H/5 * * * *')])])

node {
    stage('stage1'){
      echo 'Hello World'
    }
    stage('stage2'){
      def myname = 'omri'
      echo "Hello ${myname}"
    }
    stage('theend'){
       println('Goodbye world') 
    }
}
