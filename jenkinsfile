pipeline{
    agent{
        label 'worker'
    }
    options{
        retry(3)
        buildDiscarder(logRotator(daysToKeepStr: '7'))
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'NANOSECONDS')
        
    }
    triggers{
        cron('H */4 * * *')
        pollSCM('H */4 * * *')
    }
    parameters{
        string(name:'branch', defaultValue:'master')
        booleanParam(name:'unittesting', defaultValue:false)
    }
    stages{
        stage("first stage"){
            steps{
                sh "echo hello"
        }
            }
        stage("second stage"){
            steps{
                sh "sleep 10"
        }
            }
        
        
    }

}
