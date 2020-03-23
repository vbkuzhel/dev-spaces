pipeline{
    agent {label "windows"}
    stages{
        stage('hello'){
            steps{
                script{
                    withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'DHUB_PASSWORD', usernameVariable: 'DHUB_USER')]) {
                    powershell label: '', script: '''
                    write-host $env:computername
                    cd samples\\dotnetcore\\getting-started\\mywebapi
                    dir
                    docker build -t azdz .
                    docker login --username $env:DHUB_USER -p $env:DHUB_PASSWORD
                    docker tag azdz kuzhel/mywebapi:jenkins
                    docker push kuzhel/mywebapi:jenkins
                    '''
                    }//withCredentials
                }//script
            }//steps
        }//stage
    }//stages
}//stages