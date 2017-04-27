def func1() {
  sh('ls')
}
env.TEST = 'asd'
mail bcc: '', body: "${env.TEST}", cc: '', from: 'shutit-jenkins@jenkins.meirionconsulting.tk', replyTo: '', subject: 'Build OK', to: 'ian.miell@gmail.com'
usenode='welles'
pipeline {
  agent any
  stages {
    stage('1') {
      steps {
        script {
          try {
            timeout(time: 5, unit: 'SECONDS') {
              node(usenode) {
              func1()
              sh('ls')
              }
            }
          } catch(err) {
            usenode='cage'
          }
          node(usenode) {
            input('ok')
            func1()
          }
        }
      }
    }
  }
}
