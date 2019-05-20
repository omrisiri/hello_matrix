properties([[$class: 'JiraProjectProperty'], parameters([string(defaultValue: 'master', description: '', name: 'branch_name', trim: true)])])
node('docker') {
    stage('Prepare'){
      echo "Build job with branch ${branch_name}"
      git 'https://github.com/heroku/node-js-sample.git', branch: ${branch_name}
    }
    stage('stage2'){
        parallel firstBranch: {
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
           sh 'ls -la '
           println('Goodbye world') 
        }
    }
}
