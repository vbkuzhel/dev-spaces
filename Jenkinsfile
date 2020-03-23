pipeline{
    agent {label "windows"}
    stages{
        stage('hello'){
            steps{
                script{
                    powershell label: '', script: '''
                    write-host $env:computername
                    cd samples\\dotnetcore\\getting-started\\mywebapi
                    dir
                    '''
                }//script
            }//steps
        }//stage
    }//stages
}//stages