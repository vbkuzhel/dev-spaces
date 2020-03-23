pipeline{
    agent {label "windows"}
    stages{
        stage('hello'){
            steps{
                script{
                    powershell label: '', script: 'write-host $env:computername'
                }//script
            }//steps
        }//stage
    }//stages
}//stages