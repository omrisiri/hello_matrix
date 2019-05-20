properties([[$class: 'JiraProjectProperty'], parameters([string(defaultValue: 'master', description: '', name: 'branch_name', trim: true)])])
node('docker') {

    stage('Prepare'){
      echo "Build job with branch ${branch_name}"
      // git 'https://github.com/heroku/node-js-sample.git', 
      git branch: 'master', 'https://github.com/heroku/node-js-sample.git'
    }
    stage('stage2'){
        parallel firstBranch: {
          sh 'ls -la '
        }, secondBranch: {
          sh 'ls -la '
       }
    }
    stage('theend'){
        node('master') {
           sh 'ls -la '
           println('Goodbye world') 
        }
    }
}
