def test = [:]

test["a"] = {
    stage ("a") {
        stage ("ab") {
            sh "echo stage abc"
        }
        stage ("xyz") {
            sh "echo stage xyz"
        }
    }
}

test["b"] = {
    stage ("b") {
        stage ("bb") {
            sh "echo stage bb"
        }
        stage ("bxz") {
            sh "echo stagebxyz"
        }
    }
}
node {
   //stage 'start'
    stage ('download Code') {
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'AuthorInChangelog']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '4d6abab6-ea34-47ae-be6e-d5e2ffe50613', url: 'https://github.com/igarciar/Poc-Proyect4.git']]])
   }
   parallel test
     stage ('middle') {
       sh "echo middle"
   }
    stage ('maven') {
       sh "echo middle"
   }
   
}
